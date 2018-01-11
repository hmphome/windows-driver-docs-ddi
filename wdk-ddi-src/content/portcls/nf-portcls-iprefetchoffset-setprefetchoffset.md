---
UID: NF.portcls.IPreFetchOffset.SetPreFetchOffset
title: IPreFetchOffset::SetPreFetchOffset method
author: windows-driver-content
description: The SetPreFetchOffset method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.
old-location: audio\iprefetchoffset_setprefetchoffset.htm
old-project: audio
ms.assetid: fef8e8b8-7e79-4d88-b643-9b371e4297fd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPreFetchOffset, IPreFetchOffset::SetPreFetchOffset, SetPreFetchOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPreFetchOffset.SetPreFetchOffset
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
---

# IPreFetchOffset::SetPreFetchOffset method



## -description
The <code>SetPreFetchOffset</code> method sets the prefetch offset, which is the number of bytes of data separating the write cursor from the play cursor in a DirectSound output stream.



## -syntax

````
VOID SetPreFetchOffset(
  [in] ULONG PreFetchOffset
);
````


## -parameters

### -param PreFetchOffset [in]

Specifies the prefetch offset size in bytes.


## -returns
None


## -remarks
A WavePci miniport driver calls the <code>SetPreFetchOffset</code> method to specify the prefetch offset of a hardware-accelerated DirectSound output stream.

The prefetch offset is the number of bytes of data separating the write cursor from the play cursor in the audio device's hardware buffer:

The write cursor specifies the buffer position into which a DirectSound application can safely write the next sound sample.

The play cursor specifies the buffer position of the sound sample that is currently being played by the audio device.

For more information about write cursors and play cursors, see <a href="..\ksmedia\ns-ksmedia-ksaudio_position.md">KSAUDIO_POSITION</a>.

For information about using <code>SetPreFetchOffset</code> to control a DirectSound stream's prefetch offset, see <a href="https://msdn.microsoft.com/92a0163f-29b1-4e15-88ab-67e1097d015e">Prefetch Offsets</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iprefetchoffset.md">IPreFetchOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksaudio_position.md">KSAUDIO_POSITION</a>
</dt>
<dt>
<a href="audio.iminiportwavepcistream_getposition">IMiniportWavePciStream::GetPosition</a>
</dt>
<dt>
<a href="audio.iportwavepcistream_getmapping">IPortWavePciStream::GetMapping</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPreFetchOffset::SetPreFetchOffset method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
