---
UID: NF.printerextension.IPrintSchemaTicket.GetCapabilities
title: IPrintSchemaTicket::GetCapabilities method
author: windows-driver-content
description: Gets an IPrintSchemaCapabilities object that represents the printer capabilities based on the current settings of this IPrintSchemaTicket object.
old-location: print\iprintschematicket_getcapabilities.htm
old-project: print
ms.assetid: 5556BD5E-6489-4CCF-8C62-DDA53AD9F368
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket::GetCapabilities, GetCapabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintSchemaTicket.GetCapabilities
req.alt-loc: printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# IPrintSchemaTicket::GetCapabilities method



## -description
Gets an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object.



## -syntax

````
HRESULT GetCapabilities(
  [out, retval] IPrintSchemaCapabilities **ppPrintCapabilities
);
````


## -parameters

### -param ppPrintCapabilities [out, retval]

The returned <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks
Because this method retrieves a new PrintCapabilities document every time it is invoked, it is recommended that you invoke this method only when the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object has been modified.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>
</dt>
<dt>
<a href="print.iprintschemafeature_selectedoption">IPrintSchemaFeature::SelectedOption</a>
</dt>
<dt>
<a href="print.iprintschemaelement_xmlnode">IPrintSchemaElement::XmlNode</a>
</dt>
<dt>
<a href="print.iprintschematicket_put_jobcopiesalldocuments">IPrintSchemaTicket::put_JobCopiesAllDocuments</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::GetCapabilities method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
