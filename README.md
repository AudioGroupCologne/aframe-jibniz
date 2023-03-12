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

IBNIZ Live Coding objects can also be spawned into the environment. See Glitch example for implementation.

###### Attributes:

| Property | Description | Default |
| ------------- | ------------- | ------------- |
| code | current source code  | _ |


## Run
See the VERZNIZ metaverse system for implementation: [VERNIZ](https://github.com/AudioGroupCologne/VERSNIZ) 

## Acknowledgements

This is a port of flupe's JavaScript implementation of the IBNIZ VM, found at [jibniz](https://github.com/flupe/jibniz) 
