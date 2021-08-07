---
title: HBO - Media Manifest Metadata
permalink: hbo-mmc.html
layout: portfolio-specs
folder: mydoc
---

The purpose of this document is to document and define **Redacted** requirements for the successful delivery of content and technical metadata using MovieLabs Media Manifest Core (MMC).

### Media Manifest Core

**Redacted** has standardized on MMC, which is an industry-standard from the MovieLabs family of specifications, to accompany all packages or assets delivered to the **Redacted**. The Media Manifest Core has a simple metadata structure able to express relationships between media elements and technical metadata that is discrete from the physical form and location of the assets. WarnerMedia is currently utilizing [Media Manifest version 1.8.pdf](https://movielabs.com/md/manifest/v1.8/Manifest_v1.8.pdf).

**Redacted**’s manifest requirement is a well-defined subset of the overall content in MMC. Specifically, we support the following key features:

* **Inventory -** The inventory of media, including video, audio, text tracks, and artwork.
  * Video - Description of the parent video track.
  * Audio - Description of one or more audio tracks.
  * Subtitle - Metadata about subtitle tracks.
  * Image - Description of the images.
* **Presentations**
  * Markers - Representation of timed events in the video track.
* **Picture Groups -** Metadata about artwork referenced in inventory.

In addition to metadata requirements, **Redacted** relies on consistent taxonomy and controlled vocabulary for various fields. For accepted values, refer to the **Controlled Vocabulary** section.

### Identifiers

As prescribed by the MMC specification, the primary requirement for identifiers is global uniqueness. In order to comply with the MMC specification, providers MUST supply identifiers in the following format:

**md:[idtype]:[scheme]:[SSID]:[additional information]**

### Parameter Definitions

`<idtype>` - the type of identifier. See Common Metadata for more details on identifier types.

`<scheme>` - the namespace of the identifier. We accept registered identifiers with EIDR, TMS, Gracenote or any Common Metadata recognized naming scheme. We also accept the private house scheme used in the distributor org.

`<SSID>` - The scheme specific ID or SSID is a string that corresponds with IDs in scheme. For example: **Redacted** for EIDR scheme

#### Example

**md: id:EIDR-S:58D1-A4D9-E968-F592-5435-M**

The parent ContentID MUST be the identification of the edit-level entity in the distributor org. It MUST be specified within the Inventory Metadata-type, which can contain: Content ID, metadata, or reference a metadata container.

### Inventory Metadata

This purpose of this section is to contain either Basic Metadata, or a container reference to Basic Metadata. Contributors to **Redacted** MUST use this section of the MMC to provide the Content ID, Work Type and distribution organization.

### Audio

This section describes the two tracks for audio. The first example is for 5.1 Surround English and the second is for Dual Mono Spanish.

#### 5.1 Surround English Snippet

```
<Audio AudioTrackID="md:audtrackid:eidr-x:10.5240/961B-5417-8551-0544-8586-V:composite-5.1.en">
   <Type>primary</Type>
   <Description>5.1 Surround</Description>
   <Language>en</Language>
   <Channels>6</Channels>
   <Encoding>
      <Codec>PCM</Codec>
      <TrackReference>1</TrackReference>
      <ChannelMapping>L,R,C,LFE,LS,RS</ChannelMapping>
   </Encoding>
</Audio>
```

#### Dual Mono Spanish Snippet

```
<Audio AudioTrackID="md:audtrackid:eidr-x:10.5240/961B-5417-8551-0544-8586-V:composite-2.0DM.en">
   <Type>Primary</Type>
   <Description>Dual Mono</Description>
   <Language>es</Language>
   <Channels>2</Channels>
   <Encoding>
      <Codec>PCM</Codec>
      <TrackReference>2</TrackReference>
      <ChannelMapping>M1,M2</ChannelMapping>
   </Encoding>
</Audio>
```

### Inventory

This purpose of this section in the MMC is to provide technical details regarding the delivered assets. Several fields are required for the DTC workflow, while some are optional and are indicated accordingly.

#### Snippet

```
<Image ImageID="md:imageid:eidr-s:C124-0623-A677-69A8-0B8C-J:Logo-png">
   <Width>4320</Width>
   <Height>1300</Height>
   <Encoding>png</Encoding>
   <ContainerReference>
      <ContainerLocation>/A2017084/AustinPowersIMOM_1997_2017084_Logo_4320x1300.png</ContainerLocation>
   </ContainerReference>
</Image>
```

<table>
<caption>
  Field Descriptions
</caption>
   <thead>
      <tr>
         <th scope="col">MMC Field Name</th>
         <th scope="col">Required?</th>
         <th scope="col">Description</th>
      </tr>
   </thead>
   <tbody>
   <tr>
         <td colspan="3"><b>Video</b></td>
      </tr>
      <tr>
         <td scope="col">VideoTrackID</td>
         <td>Yes</td>
         <td>The identifier of the video track. md:videotrackid:[scheme]:[SSID]</td>
      </tr>
      <tr>
         <td scope="col">Type</td>
         <td>Yes</td>
         <td>The video type. Only primary video is accepted.</td>
      </tr>
      <tr>
         <td scope="col">SubType</td>
         <td></td>
         <td>This field may be used to further describe the primary video. (Theatrical, Broadcast, DTC, Censored).</td>
      </tr>
      <tr>
         <td scope="col">Encoding</td>
         <td>Yes</td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">Codec</td>
         <td>Yes</td>
         <td>The codec used such as JPEG2000. See accepted video codecs in the Controlled Vocabulary Section.</td>
      </tr>
      <tr>
         <td scope="col">BitRateAverage</td>
         <td></td>
         <td>Bitrate averaged over the entire track.</td>
      </tr>
      <tr>
         <td scope="col">ActualLength</td>
         <td>Yes</td>
         <td>The actual length of the track. Example: PT1H40M27.130S</td>
      </tr>
      <tr>
         <td scope="col">Picture</td>
         <td></td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">AspectRatio</td>
         <td>Yes</td>
         <td>The original aspect ratio calculated by dividing active width pixels / active height pixels. </td>
      </tr>
      <tr>
         <td scope="col">FrameRate</td>
         <td>Yes</td>
         <td>The native frame rate. Frames/seconds denoted as decimal.</td>
      </tr>
      <tr>
         <td scope="col">ActiveWidthPixels</td>
         <td>Yes</td>
         <td>Number of active width pixels.</td>
      </tr>
      <tr>
         <td scope="col">ActiveHeightPixels</td>
         <td>Yes</td>
         <td>Number of active height pixels.</td>
      </tr>
      <tr>
         <td scope="col">WidthPixels</td>
         <td>Yes</td>
         <td>Number pixel columns.</td>
      </tr>
      <tr>
         <td scope="col">HeightPixels</td>
         <td>Yes</td>
         <td>Number of pixel rows.</td>
      </tr>
      <tr>
         <td scope="col">Progressive</td>
         <td>Yes</td>
         <td>Boolean indicating picture scan type. “true”=progressive, “false”=interlaced</td>
      </tr>
      <tr>
         <td colspan="3"><b>Subtitle</b></td>
      </tr>
      <tr>
         <td scope="col">SubtitleTrackId</td>
         <td>Yes</td>
         <td>The identifier of the subtitle track. The format - md:subtrackid:[scheme]:[SSID]</td>
      </tr>
      <tr>
         <td scope="col">Type</td>
         <td>Yes</td>
         <td>The purpose of the Subtitle. See accepted subtitle types in the Controlled Vocabulary section.</td>
      </tr>
      <tr>
         <td scope="col">FormatType</td>
         <td>Yes</td>
         <td>The subtitle format type.</td>
      </tr>
      <tr>
         <td scope="col">Language</td>
         <td>Yes</td>
         <td>Language of the subtitle track.</td>
      </tr>
      <tr>
         <td scope="col">ContainerReference</td>
         <td>Yes</td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">ContainerLocation</td>
         <td>Yes</td>
         <td>Contains a URL referencing the location of the file.</td>
      </tr>
      <tr>
         <td colspan="3"><b>Audio</b></td>
      </tr>
      <tr>
         <td scope="col">AudioTrackID</td>
         <td>Yes</td>
         <td>The attribute of the audio track. The format md:audtrackid:[scheme]:[SSID]:[info]</td>
      </tr>
      <tr>
         <td scope="col">Type</td>
         <td>Yes</td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">SubType</td>
         <td></td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">Language</td>
         <td>Yes</td>
         <td>Indicates how channels are mapped to intended speaker locations.</td>
      </tr>
      <tr>
         <td scope="col">Encoding</td>
         <td></td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">Codec</td>
         <td></td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">Channels</td>
         <td>Yes</td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">TrackReference</td>
         <td>Yes</td>
         <td>An integer indicating the target track’s number/position.</td>
      </tr>
      <tr>
         <td scope="col">ChannelMapping</td>
         <td></td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">ContainerReference</td>
         <td>Yes</td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">ContainerLocation</td>
         <td>Yes</td>
         <td>Contains a URL referencing the location of the file.</td>
      </tr>
      <tr>
         <td colspan="3"><b>Image</b></td>
      </tr>
      <tr>
         <td scope="col">ImageID</td>
         <td>Yes</td>
         <td>The identifier of the image. md:imageid:[schema]:[SSID]:[info]</td>
      </tr>
      <tr>
         <td scope="col">Width</td>
         <td>Yes</td>
         <td>The image width.</td>
      </tr>
      <tr>
         <td scope="col">Height</td>
         <td>Yes</td>
         <td>The image height.</td>
      </tr>
      <tr>
         <td scope="col">Purpose</td>
         <td>Yes</td>
         <td>The image purpose. See accepted types in the Controlled Vocabulary section.</td>
      </tr>
      <tr>
         <td scope="col">Encoding</td>
         <td>Yes</td>
         <td>The encoding method or format.</td>
      </tr>
      <tr>
         <td scope="col">ContainerReference</td>
         <td>Yes</td>
         <td></td>
      </tr>
      <tr>
         <td scope="col">ContainerLocation</td>
         <td>Yes</td>
         <td>Contains a URL referencing the location of the file.</td>
      </tr>
   </tbody>
</table> 

### Markers

A marker identifies a significant time-code event within a work. A single, “marked” frame may represent one point in time (a single frame’s timecode label) or may be one of a pair of markers describing the start and end of a segment of interest.
 
* Distinct segments described by first-frame (FF) and last-frame (LF) notation may overlap.

* Composition segments (declared using the in-point label FFOC and the out-point label LFOC) MUST bracket a single, contiguous segment of program content. If one were to play all composition segments back-to-back, playback MUST not include non-program material nor exclude any program content.

*  Logos, slates, cards and so forth are not program content and SHOULD NOT appear in a playlist of composition segments. However, they MUST be “marked.”

* End-credits and start-credits are not distinct composition segments and MUST be marked independently of the composition segment in which they appear.
 
**Redacted** supports label types described in SMPTE ST 2067-3 and will not recognize or process a distributor’s proprietary marker labels. Currently-recognized labels are listed in the Controlled Vocabulary section below.
 
In addition to the SMPTE labels, we support two additional, non-SMPTE labels (a pair) which allow us to distinguish black outside of the bounds of the program from commercial black. The two labels are:
 
 1. FFVB – First frame of video black
 1. LFVB – Last frame of video black

#### Snippet

```
<Marker>
   <Timecode dropframe="false">00:59:20:00</Timecode>
   <DisplayLabel language="en">START: SLATE</DisplayLabel>
   <Label>FFHS</Label>
</Marker>
```