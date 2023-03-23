# aframe-jibniz

IBNIZ live coding A-Frame component, for live coding IBNIZ in the metaverse.


## Dependencies

Use this component in [A-Frame](https://aframe.io), together with the [Networked-Aframe](https://github.com/networked-aframe/networked-aframe) library and the [Aframe-Super-Keyboard](https://github.com/supermedium/aframe-super-keyboard) component.  

## Usage

### Add the ibniz component to your desired A-Frame entity to include the IBNIZ Live Coding environment. A child entity including the Super-Keyboard component needs to be attached:

```html
    <a-scene>
        <a-entity ibniz="">
          <a-entity
              id="keyboard"
              super-keyboard="hand:; imagePath:./;keyColor:#FFFFFF;keyBgColor:#FFFFFF;align:center"
              ibniz-keyboard="keyColor:#FFFFFF;keyBgColor:#FFFFFF"
              position="0 -0.6 +2.6"
              rotation="-30 0 0"
              scale="3 3 3"
            ></a-entity>
	</a-entity>
    </a-scene>
```


###### Attributes:

| Property | Description | Default |
| ------------- | ------------- | ------------- |
| code | current source code  | _ |

### Add template of the live-coding object, including an Aframe-Super-Keyboard component, to your A-Scene assets:

```html
    <a-assets>
        <template id="ibniz-template">
          <a-entity
            class="raycastable"
            geometry="primitive: sphere"
            material="src:;displacementMap:"
            text="value:Hello World;side:double;xOffset:7.5;width:10"
            sound="autoplay: true;loop:true"
            canvas-updater
            resonance-audio-src="
            src:;
            loop: true;
            autoplay: true;"
            ibniz=""
          >
            <a-entity
              id="keyboard"
              super-keyboard="hand:; imagePath:./;keyColor:#FFFFFF;keyBgColor:#FFFFFF;align:center"
              ibniz-keyboard="keyColor:#FFFFFF;keyBgColor:#FFFFFF"
              position="0 -0.6 +2.6"
              rotation="-30 0 0"
              scale="3 3 3"
            ></a-entity>
          </a-entity>
        </template>

```

Additionally a canvas objects needs to included into the assets:

```html
        <canvas id="my-canvas" crossorigin="anonymous"></canvas>
      </a-assets>
```

### Add template the Networked-Aframe NAF.shemas: 


```javascript
        if (!NAF.schemas.hasTemplate("#ibniz-template")) {
          NAF.schemas.add({
            template: "#ibniz-template",
            components: [
              "position",
              {},
              "ibniz",
              {
                property: "code",
                property: "geo",
              },
            ],
          });
        }
```

### Live coding objects can be spawned into the environment by using the `ibniz-persistent` component: 

```html
      <!-- Player Setting -->
      <a-entity
        id="player"
        networked="template:#avatar-template;attachTemplateToLocal:false;"
        camera
        position="0 1.6 0"
        spawn-in-circle="radius:3"
        ibniz-persistent="template:#ibniz-template"
        wasd-controls
        look-controls
      >
```

###### Attributes:

| Property | Description | Default |
| ------------- | ------------- | ------------- |
| template | template of the object to be spawned  | '' |
| keyCode | key code to trigger spawned object  | 32 (space) |

## Run
See the VERZNIZ metaverse system for implementation: [VERNIZ](https://github.com/AudioGroupCologne/VERSNIZ) 

## Acknowledgements

This is a port of flupe's JavaScript implementation of the IBNIZ VM, found at [jibniz](https://github.com/flupe/jibniz) 
