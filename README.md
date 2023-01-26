# Decentraland scene

This folder contains all the necessary files to launch a Decentraland scene.

## Try it out

**Install the CLI**

Download and install the Decentraland CLI by running the following command:

```bash
npm i -g decentraland
```

**Previewing the scene**

Open this folder on the command line, then run:

```
dcl start
```

Any dependencies are installed and then the CLI opens the scene in a new browser tab.

## Guide to Create Your First Scene

To create your first scene using the Decentraland Editor, follow these steps. Make sure you’ve installed the Decentraland editor, then:

1. Open a Visual Studio Code window on an empty folder.
2. Select the Decentraland tab on Visual Studio’s left margin sidebar
3. Click __Create Project__
4. The editor will prompt you about what kind of project to create. Select __Scene__ then pick the first option, __Cube Spawner__.
5. Preview the 3D scene by clicking __Run Scene__ in the Decentraland tab of Visual Studio Code.

### Edit the scene

- Open the `src/game.ts` file from your scene folder.
- Change anything you want from this code, for example change the x position of the first cube entity that’s spawned (on line 42). If you kept the preview running in an open tab, you should now see the changes show in the preview.
- Download this 3D model of an avocado from the scene’s GitHub repo in glTF format [link](https://github.com/decentraland-scenes/avocado/raw/main/Avocado.zip).
- Create a new folder under your scene’s directory named `/models`. Extract the downloaded file and drop all of its contents in that folder. Note that there are several files that make up the 3D model, all of them must be in the same path.
- At the end of your scene’s code, add the following lines:

```ts
let avocado = new Entity()
avocado.addComponent(new GLTFShape("models/avocado.gltf"))
avocado.addComponent(
  new Transform({
    position: new Vector3(3, 1, 3),
    scale: new Vector3(13, 13, 13),
  })
)
engine.addEntity(avocado)
```

## Deploy to Decentraland

If you own any parcels of land in Decentraland, or have permissions to deploy to someone else's, you can publish this project.

1. Make sure the scene parcels in `scene.json` match those you own or have permissions on.
2. Run `dcl deploy` on the project folder
3. This will open a browser tab to confirm. Metamask will prompt you to sign.
   > Note: Make sure you are using the wallet that owns the parcels or has permissions.

### Deploy to a free server

If you don't own parcels in Decentraland or are not ready to publish your scene to the world, you can share your creations by uploading your scenes to a free hosting service.

See [Upload a preview](https://docs.decentraland.org/development-guide/deploy-to-now/) for instructions on how to do this.

## Resources

Learn more about how to build your own scenes in our [documentation](https://docs.decentraland.org/) site.

Find more example scenes, tutorials and helper libraries in the [Awesome Repository](https://github.com/decentraland-scenes/Awesome-Repository).

If you need any help, join [Decentraland's Discord](https://dcl.gg/discord), where you'll find a vibrant community of other creators who are eager to help. You're sure to find help in the #SDK support channel.

## Copyright info

This scene is protected with a standard Apache 2 licence. See the terms and conditions in the [LICENSE](/LICENSE) file.