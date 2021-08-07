---
title: HBO - Licensed Content (SDR)
permalink: hbo-sdr.html
layout: portfolio-specs
folder: mydoc
---

The purpose of this document is to facilitate and define **Redacted** requirements for the successful acquisition of Standard Dynamic Range (SDR) Licensed Content from external parties. This specification establishes the composition and technical requirements for all aspects of the delivery to which external parties must comply to complete the content acquisition process.

This specification is not intended to provide guidance on delivering High Dynamic Range, Stereoscopic 3D or multi-language component content to **Redacted**. For additional Contribution Specifications covering these deliveries please reach out to **Redacted**.

### Quality Requirements

It is **Redacted** intent to acquire the highest quality masters that preserve the original artistic intent while providing a premium viewing experience to the consumer. To meet **Redacted** perceptual and measured quality standards content delivered must conform to the specifications outlined in this document. In preparing content for delivery and to preserve the highest quality it is strongly preferred that all unnecessary transformations or processing that results in the degradation to the master quality be avoided.

### Expected Deliverables

A complete and valid delivery SHALL include:

1. Master File (JPEG 2000 MXF OP1a or ProRes 422 HQ)
2. English Closed Caption file (.scc)
3. Latin Spanish Closed Caption file (.scc)
4. Descriptive Metadata
5. Images / Artwork

### Master Technical Specifications

1. Content MUST be delivered in the Native Frame Rate and Original Aspect Ratio.
2. Native SD content MUST be upconverted and delivered as HD (1920x1080) with pillar-box.
3. Content finished as UHD SHOULD be delivered as UHD. Note that UHD content will be presented as HD until such time as the service supports UHD.
4. The frame rate MUST be both continuous and constant throughout the duration of the program.
5. Theatrical content MUST be delivered as a continuous program. Theatrical content formatted with Ad breaks will be rejected.
6. Episodic content MAY be delivered formatted with Ad breaks ONLY if a continuous program is not available. Ad break duration SHOULD be 15 frames but MUST NOT exceed 1 second from the beginning of fade down to end of fade up.
7. Metadata in the file header MUST accurately indicate:
  * Scan Type
  * Scan Order 
  * Display Aspect Ratio

### Master File Format

#### Option 1: JPEG2000 MXF OP1a

<table>
<caption>
  Video Specification
</caption>
  <tbody>
    <tr>
      <th>Codec</th>
      <td>JPEG 2000</td>
    </tr>
    <tr>
        <th>Container</th>
        <td>MXF OP1a (Conforming to SMPTE ST 378: 2004)</td>
      </tr>
     <tr>
         <th>Frame Rate</th>
         <td>Original/Native</td>
       </tr>
    <tr>
         <th>Scan Type</th>
         <td>Native (Progressive or Interlaced)</td>
       </tr>
    <tr>
         <th>Aspect Ratio</th>
         <td>Original/Native</td>
       </tr>
     <tr>
         <th>Resolution</th>
         <td>HD (1920 x1080) | UHD (3840 x 2160)</td>
       </tr>
       <tr>
         <th>Max Bit Rate</th>
         <td>HD 250Mbps | UHD 800Mbps (BCP Level 5)</td>
       </tr>
       <tr>
         <th>Rate Control</th>
         <td>Variable Bit Rate (VBR)</td>
       </tr>
       <tr>
         <th>Chroma Bit Depth</th>
         <td>10-bit</td>
       </tr>
       <tr>
         <th>Color Coding/Space</th>
         <td>Y'CbCr 4:2:2/Legal Range</td>
       </tr>
       <tr>
         <th>Color Matrix/Primaries</th>
         <td>ITU-R BT.709</td>
       </tr>
  </tbody>
</table>

<table>
<caption>
  Audio Specification
</caption>
<tbody>
  <tr>
    <th>Codec</th>
    <td>Linear PCM</td>
  </tr>
  <tr>
      <th>Sample Bit Depth</th>
      <td>24-bit</td>
    </tr>
   <tr>
       <th>Sample Rate</th>
       <td>48kHz</td>
     </tr>
</tbody>
</table>

##### JPEG 2000 Qualification

For providers wishing to deliver JPEG 2000 MXF OP1a masters, an on-boarding output qualification process is required before any content can be delivered. Please contact **Redacted** to initiate the qualification process.

#### Option 2: ProResHQ

<table>
<caption>
  Video Specification
</caption>
  <tbody>
    <tr>
      <th>Codec</th>
      <td>ProRes 422 HQ</td>
    </tr>
    <tr>
        <th>Container</th>
        <td>QuickTime MOV</td>
      </tr>
     <tr>
         <th>Frame Rate</th>
         <td>Original/Native</td>
       </tr>
    <tr>
         <th>Scan Type</th>
         <td>Native (Progressive or Interlaced)</td>
       </tr>
    <tr>
         <th>Aspect Ratio</th>
         <td>Original/Native</td>
       </tr>
     <tr>
         <th>Resolution</th>
         <td>HD (1920 x1080) | UHD (3840 x 2160)</td>
       </tr>
       <tr>
         <th>Max Bit Rate</th>
         <td>HD ~ 176 to 220Mbps | UHD ~ 796 to 880Mbps</td>
       </tr>
       <tr>
         <th>Rate Control</th>
         <td>Variable Bit Rate (VBR)</td>
       </tr>
       <tr>
         <th>Chroma Bit Depth</th>
         <td>10-bit</td>
       </tr>
       <tr>
         <th>Color Coding/Space</th>
         <td>Y'CbCr 4:2:2/Legal Range</td>
       </tr>
       <tr>
         <th>Color Matrix/Primaries</th>
         <td>ITU-R BT.709</td>
       </tr>
  </tbody>
</table>

<table>
<caption>
  Audio Specification
</caption>
<tbody>
  <tr>
    <th>Codec</th>
    <td>Linear PCM</td>
  </tr>
  <tr>
      <th>Sample Bit Depth</th>
      <td>24-bit</td>
    </tr>
   <tr>
       <th>Sample Rate</th>
       <td>48kHz</td>
     </tr>
</tbody>
</table>

### Slate

First frame of video MUST begin with a visual slate. Slate SHALL contain:

* Program title:
* Episode No (if applicable):
* Production Company:
* Program Run Time:
* Aspect Ratio:
* Audio Track Layout: [Language/Type - Configuration]
* Textless Included

### Audio Technical Specifications

1.	Each Soundfield group MUST be arranged into a single track. e.g. 5.1 would be 1 track with 6 channels.
2.	Stereo labels MUST match the method used to create the Soundfield: LtRt for matrixed downmix and LR for stereo mix.
3.	All audio channels MUST be labeled in the file metadata and adhere to Multichannel Audio Labeling specified in [SMPTE ST 377-4:2012](https://ieeexplore.ieee.org/document/7290582).
4.	All native mono content MUST be delivered as Dual Mono and labeled as ‘M1’ and ‘M2’. Any content delivered with a single mono channel will be rejected.
5.	All audio tracks MUST conform (be synchronous) with video and have the same duration.
6.	Where both exist, a near field mix is preferred over a Theatrical mix.
7.	Primary 5.1 surround, Music & Effects, Latin Spanish and Audio Description tracks are required where available.
8.	Content with 5.1 surround MUST be provided with a separate, corresponding 2.0 track.
9.	Target Audio loudness MUST conform to [ITU-1770-3](https://www.itu.int/rec/R-REC-BS.1770-3-201208-S/en) specifications where:
  * Target loudness for 2 Channel Program Audio (e.g. LtRt) MUST be ∑ -24 LKFS +/- 2 dB
  * Target loudness for 5.1 Channel Program Audio MUST be ∑ -24 LKFS +/- 2 dB (minus LFE)
  * True Peak DOES NOT exceed -2 dBTP



