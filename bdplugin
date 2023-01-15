/**
 * @name ToggleFullscreen
 * @author joeru
 * @description toggle fullscreen on selected videos with keybind
 * @version 0.0.1
 */

 config = {
  info: {
    name: "Toggle Fullscreen Video",
    id: "FullscreenToggle",
    description: "toggle fullscreen on selected video",
    version: "0.0.1",
    author: "joeru",
    updateUrl: "https://raw.githubusercontent.com/Farcrada/DiscordPlugins/master/Double-click-to-edit/DoubleClickToEdit.plugin.js"

  }
},


    module.exports = class ToggleFullscreen {
      load() {
        // Called when the plugin is activated (including after reloads)
        BdApi.alert("fullscreen plugin YURPP");

      } 
      start () {
        try { 
          this.selectedClass = Webpack.getModule(Filters.byProps("message", "selected")).selected;

        


        }
        catch (err) {
          try {
            console.error("Attempting to stop after starting error...", err);
            this.stop();
          }
          catch (err) {
            console.error(config.info.name + ".stop()", err);
          }
        }
      }
      stop() { }
      getSettingsPanel(){
        return() => {
      const [editEnableModifier, setEditEnableModifier] = React.useState(this.FullscreenToggle)



      return[
        //Edit
        React.createElement(this.SwitchItem, {
          //The state that is loaded with the default value
          value: editEnableModifier,
          note: "Enable modifier for double clicking to edit",
          //Since onChange passes the current state we can simply invoke it as such
          onChange: (newState) => {
            //Saving the new state
            this.ToggleFullscreen = newState;
            Data.save(config.info.id, "ToggleFullscreen", newState);
            setEditEnableModifier(newState);
          }
        }, "Enable Edit Modifier"),
        React.createElement(this.FormTitle, {
          disabled: !editEnableModifier,
          tag: "h3"
        }, "Modifer to hold to edit a message"),
        React.createElement(this.RadioItem, {
          disabled: !editEnableModifier,
          value: editModifier,
        
         }),
        ]
     }
    }
  handler(e) {
    //Check if we're not double clicking
    if (typeof (e?.target?.className) !== typeof ("") ||
      blacklist.some(nameOfClass => e?.target?.className?.indexOf?.(nameOfClass) > -1))
      return;

    //Target the message
    const messageDiv = e.target.closest('li > [class^=message]');

    //If it finds nothing, null it.
    if (!messageDiv)
      return;
    //Make sure we're not resetting when the message is already in edit-mode.
    if (messageDiv.classList.contains(this.selectedClass))
      return;

    //Basically make a HTMLElement/Node interactable with it's React components.
    const instance = BdApi.getInternalInstance(messageDiv);
    //Mandatory nullcheck
    if (!instance)
      return;








  }   
}
