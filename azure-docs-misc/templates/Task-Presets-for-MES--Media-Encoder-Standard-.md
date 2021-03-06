---
title: "Task Presets for MES (Media Encoder Standard)"
ms.custom: na
ms.date: 2016-03-08
ms.prod: azure
ms.reviewer: na
ms.service: media-services
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cfabc2d6-d7cd-4e73-a1f0-32ec13697758
caps.latest.revision: 14
author: juliako
manager: erikre
translation.priority.mt: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-tw
---
# Task Presets for MES (Media Encoder Standard)
`Media Encoder Standard` defines a set of encoding presets you can use when creating encoding jobs  
  
 The XML or JSON present strings should be based on the presets shown in the files below. You can pass presets with custom values to the encoder (the values must be valid.) For explanations of what each element in these presets means, and the valid values for each element, see the [Media Encoder Standard Schema](../templates/Media-Encoder-Standard-Schema.md) topic.  
  
> [!NOTE]
>  When using a preset for 4k encodes, you should get the `S3` reserved unit type. For more information, see [How to Scale Encoding](https://azure.microsoft.com/en-us/documentation/articles/media-services-portal-encoding-units).  
  
 When working with Media Encoder Standard, rotation is enabled by default. If your video has been recorded on a smartphone or other mobile device in Portrait mode, then these presets will, by default, rotate them to Landscape mode prior to encoding (unlike, when you work with Azure Media Encoder, where video rotation is a manual operation, as documented in [this](http://azure.microsoft.com/blog/2014/08/21/advanced-encoding-features-in-azure-media-encoder/) blog, under “Video Rotation”).  
  
 The preset names map to presets shown in the following topics.  
  
 [H264 Multiple Bitrate 1080p Audio 5.1](../templates/H264-Multiple-Bitrate-1080p-Audio-5.1.md) produces a set of 8 GOP-aligned MP4 files, ranging from 6000 kbps to 400 kbps, and AAC 5.1 audio.  
  
 [H264 Multiple Bitrate 1080p](../templates/H264-Multiple-Bitrate-1080p.md) produces a set of 8 GOP-aligned MP4 files, ranging from 6000 kbps to 400 kbps, and stereo AAC audio.  
  
 [H264 Multiple Bitrate 16x9 for iOS](../templates/H264-Multiple-Bitrate-16x9-for-iOS.md) produces a set of 8 GOP-aligned MP4 files, ranging from 8500 kbps to 200 kbps, and stereo AAC audio.  
  
 [H264 Multiple Bitrate 16x9 SD Audio 5.1](../templates/H264-Multiple-Bitrate-16x9-SD-Audio-5.1.md) produces a set of 5 GOP-aligned MP4 files, ranging from 1900 kbps to 400 kbps, and AAC 5.1 audio.  
  
 [H264 Multiple Bitrate 16x9 SD](../templates/H264-Multiple-Bitrate-16x9-SD.md) produces a set of 5 GOP-aligned MP4 files, ranging from 1900 kbps to 400 kbps, and stereo AAC audio.  
  
 [H264 Multiple Bitrate 4K Audio 5.1](../templates/H264-Multiple-Bitrate-4K-Audio-5.1.md) produces a set of 12 GOP-aligned MP4 files, ranging from 20000 kbps to 1000 kbps, and AAC 5.1 audio.  
  
 [H264 Multiple Bitrate 4K](../templates/H264-Multiple-Bitrate-4K.md) produces a set of 12 GOP-aligned MP4 files, ranging from 20000 kbps to 1000 kbps, and stereo AAC audio.  
  
 [H264 Multiple Bitrate 4x3 for iOS](../templates/H264-Multiple-Bitrate-4x3-for-iOS.md) produces a set of 8 GOP-aligned MP4 files, ranging from 8500 kbps to 200 kbps, and stereo AAC audio.  
  
 [H264 Multiple Bitrate 4x3 SD Audio 5.1](../templates/H264-Multiple-Bitrate-4x3-SD-Audio-5.1.md) produces a set of 5 GOP-aligned MP4 files, ranging from 1600 kbps to 400 kbps, and AAC 5.1 audio.  
  
 [H264 Multiple Bitrate 4x3 SD](../templates/H264-Multiple-Bitrate-4x3-SD.md) produces a set of 5 GOP-aligned MP4 files, ranging from 1600 kbps to 400 kbps, and stereo AAC audio.  
  
 [H264 Multiple Bitrate 720p Audio 5.1](../templates/H264-Multiple-Bitrate-720p-Audio-5.1.md) produces a set of 6 GOP-aligned MP4 files, ranging from 3400 kbps to 400 kbps, and AAC 5.1 audio.  
  
 [H264 Multiple Bitrate 720p](../templates/H264-Multiple-Bitrate-720p.md) produces a set of 6 GOP-aligned MP4 files, ranging from 3400 kbps to 400 kbps, and stereo AAC audio.  
  
 [H264 Single Bitrate 1080p Audio 5.1](../templates/H264-Single-Bitrate-1080p-Audio-5.1.md) produces a single MP4 file with a bitrate of 6750 kbps, and AAC 5.1 audio.  
  
 [H264 Single Bitrate 1080p](../templates/H264-Single-Bitrate-1080p.md) produces a single MP4 file with a bitrate of 6750 kbps, and stereo AAC audio.  
  
 [H264 Single Bitrate 4K Audio 5.1](../templates/H264-Single-Bitrate-4K-Audio-5.1.md) produces a single MP4 file with a bitrate of 18000 kbps, and AAC 5.1 audio.  
  
 [H264 Single Bitrate 4K](../templates/H264-Single-Bitrate-4K.md) produces a single MP4 file with a bitrate of 18000 kbps, and stereo AAC audio.  
  
 [H264 Single Bitrate 4x3 SD Audio 5.1](../templates/H264-Single-Bitrate-4x3-SD-Audio-5.1.md) produces a single MP4 file with a bitrate of 18000 kbps, and AAC 5.1 audio.  
  
 [H264 Single Bitrate 4x3 SD](../templates/H264-Single-Bitrate-4x3-SD.md) produces a single MP4 file with a bitrate of 18000 kbps, and stereo AAC audio.  
  
 [H264 Single Bitrate 16x9 SD Audio 5.1](../templates/H264-Single-Bitrate-16x9-SD-Audio-5.1.md) produces a single MP4 file with a bitrate of 2200 kbps, and AAC 5.1 audio.  
  
 [H264 Single Bitrate 16x9 SD](../templates/H264-Single-Bitrate-16x9-SD.md) produces a single MP4 file with a bitrate of 2200 kbps, and stereo AAC audio.  
  
 [H264 Single Bitrate 720p Audio 5.1](../templates/H264-Single-Bitrate-720p-Audio-5.1.md) produces a single MP4 file with a bitrate of 4500 kbps, and AAC 5.1 audio.  
  
 [H264 Single Bitrate 720p for Android](../templates/H264-Single-Bitrate-720p-for-Android.md) preset produces a single MP4 file with a bitrate of 2000 kbps, and stereo AAC.  
  
 [H264 Single Bitrate 720p](../templates/H264-Single-Bitrate-720p.md) produces a single MP4 file with a bitrate of 4500 kbps, and stereo AAC audio.  
  
 [H264 Single Bitrate High Quality SD for Android](../templates/H264-Single-Bitrate-High-Quality-SD-for-Android.md) produces a single MP4 file with a bitrate of 500 kbps, and stereo AAC audio..  
  
 [H264 Single Bitrate Low Quality SD for Android](../templates/H264-Single-Bitrate-Low-Quality-SD-for-Android.md) produces a single MP4 file with a bitrate of 56 kbps, and stereo AAC audio.  
  
 For more information related to Media Services encoders, see [Encoding On-Demand with Azure Media Services](https://azure.microsoft.com/en-us/documentation/articles/media-services-encode-asset/).