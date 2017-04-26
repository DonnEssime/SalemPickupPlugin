Setting up the project
1.  clone the sample repo
2. load the project in netbeans (suggested) or your favorite IDE. I will assume Netbeans in subsequent steps, but note where this made a difference.
   [Netbeans-specific] Resolve an issue: the plug-in needs to point at lsalem.jar in netbeans settings for the auto-suggest to work.
   [Eclipse-specific] Resolve an issue: the project needs a file reference to lsalem.jar. You can change this manually by editing project.properties and fixing the file.reference.lsalem.jar location to wherever it is for you.

Making the application aware of your plug-in
3. Refactor the SamplePlugin to whatever you want your plug-in to be called.
4. Edit manifest/META-INF.services/haven.plugins.Plugin to contain the name of your plugin class.

Giving your plug-in a resource file for the menu
5. Rename ./resources/src/paginae/add/hello.res to whatever you want to resource file to be called.
6. Open ./resources/src/paginae/add/<name>.res/action/action_0.data and change the following fields:
	6a) name (the tooltip when hovering over your plugin button)
	6b) hk (the ASCII code for your hotkey. don't bother with it if you're not going to use hotkeys)
	6c) ad[1] (this is the characteristic String the client will receive when the action button is clicked)
7. Edit in a nice icon to ./resources/src/paginae/add/<name>.res/image/image_0.data. Stick to a 40x40 image to be safe
8. Run the compile_resources.bat script (for windows - linux users should be able to figure out how to run the single line it calls)

And implementing the plug-in itself!
9. Write the Java code for your plug-in.
10. Build the project
11. [Netbeans] copy the .jar from ./dist to ~/Salem/plugins.

And, finally, launch the client and enjoy your plug-in!
