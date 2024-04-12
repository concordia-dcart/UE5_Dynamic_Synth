# UE5_Dynamic_Synth

A collection of modular sound devices and interactive systems built in and around MetaSounds in Unreal Engine 5.1. Levels are designed to demonstrate different methods of interaction.

### System requirements: UE 5.1+

# Sound Devices
All sound devices can be accessed UE5_DynamicSynth/Content/Synths
## Main Synth/Sequencer MetaSound

![FMSynthSequencerFull](./Screenshots/FMSynthSequencerFull.png)

### FM Synth

### Operator Parameter Input

![OpInputs](./Screenshots/OpInputs.png)

### ModMatrix Inputs

![ModMixerInputs](./Screenshots/ModMixerInputs.png)

### Algorithm Cheat Sheet

![FM Algo - Sheet1](./Screenshots/FMAlgo.png)

### Output

![FMSynth](./Screenshots/FMSynth.png)

### FM Operator Graph
![OperatorGraph](./Screenshots/OperatorGraph.png)

### Sequencer Input
![Sequencer](./Screenshots/Sequencer.png)

Sequencer Graph
![SequencerGraph](./Screenshots/SequencerGraph.png)

## Specialized Operators

### Kick Operator
![Kick Operator](./Screenshots/KickOperatorGraph.png)

### HH Operator
![HHOperatorGraph](./Screenshots/HHOperatorGraph.png)

# VariSpeedSampler

A workaround for implementing a sampler that can alter the pitch or timing of a sample independently.
![VariSpeedSampler](./Screenshots/VariSpeedSampler.png)

# Levels
All interactions described below are contained within level Blueprints
## DynamicSynth

The player can initiate 3 sequences built in Metasounds by colliding with trigger volumes. The Kick trigger volume initializes the Kick sequence as well as the Quartz clock, therefore the global sequence only begins when the player has collided with this particular volume.

All three sequences are quantized according to the main quartz clock. Subsequently, the Bass and HH sequence can be armed at any time, but will only begin playing at the beginning of a bar (relative to the transport).

A fourth trigger volume initiates a global change in tempo.

## DynamicSpeed

The player's distance from a cube at a far corner of the map determines the tempo of the looping sample. This level employs the time warping workaround built into the VariSynthSampler. Currently, the base tempo of the sample is set manually, but in the future BPM could be included in the metadata of the sample so that the base BPM can be determined procedurally.

A secondary interaction has been added to this level, the players Y position is linked to the cuttoff frequency of the looping sample.

# DynamicSpeedRamp

Similar to DynamicSpeed, DynamicSpeedRamp allows the player to initialize speed ramps by colliding with trigger volumes.



