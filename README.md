# How-to-install-plugin-on-startup-in-pterodactyl.
In this repo, you will know how to configure a egg such that in minecraft server, there will be a pre installed plugin in the plugin folder.

```
PLUGIN_NAME=<plugin_name.jar>
# Download and place the plugin
PLUGIN_URL="<link-to-the-plugin>"  # Replace with your plugin download URL
echo -e "Downloading plugin: ${PLUGIN_NAME}"

# (Optional) Check if a plugins folder exists and create it if not
if [ ! -d plugins ]; then
    mkdir plugins
fi

# Download the plugin and move it to the plugins folder using wget
wget -O temp_plugin.jar ${PLUGIN_URL}

# Check if the download was successful (non-zero size)
if [ -s temp_plugin.jar ]; then
    mv temp_plugin.jar plugins/${PLUGIN_NAME}
    echo -e "Plugin downloaded and moved successfully."
else
    echo -e "Error: Plugin download failed or resulted in an empty file."
    echo -e "Debug information:"
    ls -l temp_plugin.jar
    cat temp_plugin.jar
fi```
