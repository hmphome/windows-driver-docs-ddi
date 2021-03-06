---
UID: NF:wudfddi.IWDFWorkItem.Flush
title: IWDFWorkItem::Flush method
author: windows-driver-content
description: The Flush method returns after this interface's work item has been serviced.
old-location: wdf\iwdfworkitem_flush.htm
old-project: wdf
ms.assetid: AB79C2AE-0696-4EEC-9FC0-8A458CF19B82
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Flush method, Flush method, IWDFWorkItem interface, Flush,IWDFWorkItem.Flush, IWDFWorkItem, IWDFWorkItem interface, Flush method, IWDFWorkItem::Flush, umdf.iwdfworkitem_flush, wdf.iwdfworkitem_flush, wudfddi/IWDFWorkItem::Flush
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFWorkItem.Flush
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFWorkItem::Flush method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Flush</b> method returns after this interface's work item has been serviced.


## -parameters






## -returns



This method does not return a value.




## -remarks



If a driver calls the <b>Flush</b> method, the method does not return until a worker thread has removed the specified work item from the work-item queue and called the driver's <a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a> callback function, and the <i>OnWorkItem</i> callback function has subsequently returned after processing the work item.

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406734">IWDFWorkItem</a>



<a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a>
 

 

