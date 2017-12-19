---
UID: NS.NTIFS._FSRTL_COMMON_FCB_HEADER
title: _FSRTL_COMMON_FCB_HEADER
author: windows-driver-content
description: Do not use the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure.
old-location: ifsk\fsrtl_common_fcb_header.htm
old-project: ifsk
ms.assetid: b0b199ea-d72f-4de3-a6b1-bd22140d13cb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FSRTL_COMMON_FCB_HEADER, FSRTL_COMMON_FCB_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FSRTL_COMMON_FCB_HEADER
req.alt-loc: ntifs.h
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
---

# _FSRTL_COMMON_FCB_HEADER structure



## -description
Do not use the FSRTL_COMMON_FCB_HEADER structure outside of the <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure.  The FSRTL_COMMON_FCB_HEADER structure contains context information that a file system maintains about a file, directory, volume, or alternate data stream.  



## -syntax

````
typedef struct _FSRTL_COMMON_FCB_HEADER {
  CSHORT        NodeTypeCode;
  CSHORT        NodeByteSize;
  UCHAR         Flags;
  UCHAR         IsFastIoPossible;
  UCHAR         Flags2;
  UCHAR         Reserved  :4;
  UCHAR         Version  :4;
  PERESOURCE    Resource;
  PERESOURCE    PagingIoResource;
  LARGE_INTEGER AllocationSize;
  LARGE_INTEGER FileSize;
  LARGE_INTEGER ValidDataLength;
} FSRTL_COMMON_FCB_HEADER, *PFSRTL_COMMON_FCB_HEADER;
````


## -struct-fields

### -field NodeTypeCode

Reserved for system use. 


### -field NodeByteSize

Reserved for system use. 


### -field Flags

Bitmask of flags that indicate support for various features. This member must be a bitwise OR combination of one or more of the following values:




### -field FSRTL_FLAG_FILE_MODIFIED

Reserved for system use. 


### -field FSRTL_FLAG_FILE_LENGTH_CHANGED

Reserved for system use. 


### -field FSRTL_FLAG_LIMIT_MODIFIED_PAGES

Reserved for system use.  File system drivers (except for filter drivers) that must set or clear a limit of modified data for a file should call <a href="ifsk.ccsetdirtypagethreshold">CcSetDirtyPageThreshold</a>.


### -field FSRTL_FLAG_ACQUIRE_MAIN_RSRC_EX

Reserved for system use. 


### -field FSRTL_FLAG_ACQUIRE_MAIN_RSRC_SH

Reserved for system use. 


### -field FSRTL_FLAG_USER_MAPPED_FILE

The Cache Manager sets this flag to indicate that a view is mapped to a file. 


### -field FSRTL_FLAG_ADVANCED_HEADER

This flag indicates that the file system is using <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> instead of FSRTL_COMMON_FCB_HEADER in its file control block (FCB) structures. This flag is required because use of the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure is deprecated.


### -field FSRTL_FLAG_EOF_ADVANCE_ACTIVE

Reserved for system use. 

</dd>
</dl>

### -field IsFastIoPossible

This member must be one of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FastIoIsPossible</b>

</td>
<td>
Fast I/O is possible. 

</td>
</tr>
<tr>
<td>
<b>FastIoIsQuestionable</b>

</td>
<td>
An exclusive byte range lock exists for the file. The caller should call the file system's <b>FastIoCheckIfPossible</b> routine. 

</td>
</tr>
<tr>
<td>
<b>FastIoIsNotPossible</b>

</td>
<td>
The FCB for the file is bad, or an opportunistic lock (also called  "oplock") exists for the file. 

</td>
</tr>
</table>
 

For more information about these values, see the reference entries for <a href="ifsk.fsrtlaretherecurrentfilelocks">FsRtlAreThereCurrentFileLocks</a>, <a href="ifsk.fsrtlcopyread">FsRtlCopyRead</a>, and <a href="ifsk.fsrtlcopywrite">FsRtlCopyWrite</a>. 


### -field Flags2

Bitmask of flags that the file system sets to indicate support for various features. This member must be one or more of the following values: 




### -field FSRTL_FLAG2_DO_MODIFIED_WRITE

This flag is used together with the <b>FsContext2</b> member of the file object for the file stream as follows: 

<ul>
<li>If the <b>FsContext2</b> member of the file object is non-<b>NULL</b>, the file stream represents an open instance of a file or a directory, and the value of this flag is ignored by the operating system.</li>
<li>If the <b>FsContext2</b> member of the file object is <b>NULL</b>, and this flag is not set, the file object is a stream file object, and the stream is a modified-no-write (MNW) stream.</li>
<li>If the <b>FsContext2</b> member of the file object is <b>NULL</b>, and this flag is set, the file object is a stream file object, and the stream is writable.</li>
</ul>

### -field FSRTL_FLAG2_PURGE_WHEN_MAPPED

If this flag is set, the Cache Manager will flush and purge the cache map when a user first maps a file. 


### -field FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS

This flag indicates that the file system is using <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> instead of FSRTL_COMMON_FCB_HEADER in its FCB structures. This flag is required because use of the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure is deprecated.


### -field FSRTL_FLAG2_IS_PAGING_FILE 

If set, this FCB header is associated with a page file.

</dd>
</dl>

### -field Reserved

Reserved for system use. Drivers must set this bit-field to zero. 


### -field Version

Reserved for system use.  This bit-field is set by the <a href="ifsk.fsrtlsetupadvancedheader">FsRtlSetupAdvancedHeader</a> or <a href="ifsk.fsrtlsetupadvancedheaderex">FsRtlSetupAdvancedHeaderEx</a> macro.  Starting with Windows Vista, the value of this bit-field is FSRTL_FCB_HEADER_V1 or greater; otherwise, the value is FSRTL_FCB_HEADER_V0.  See <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> for more information.


### -field Resource

Pointer to an initialized resource variable, for which the file system supplies the storage that will be used to synchronize I/O access to the FCB. The resource variable must be allocated from nonpaged pool. 

Filter drivers should treat this member as opaque. 


### -field PagingIoResource

Pointer to an additional resource variable, for which the file system supplies the storage that will be used to synchronize paging I/O access to the FCB. The resource variable must be allocated from nonpaged pool. 

Filter drivers should treat this member as opaque. 


### -field AllocationSize

Allocation size for the file stream. 

For more information about the <b>AllocationSize</b>, <b>FileSize</b>, and <b>ValidDataLength</b> members, see <a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>.


### -field FileSize

File size of the file stream. 


### -field ValidDataLength

Valid data length of the file stream. 


## -remarks
File systems must set the <b>FsContext</b> member of every file object to point to an <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure.  This structure can be embedded inside of a file-system-specific stream context object structure (the remainder of this structure is file-system-specific). Usually, the FSRTL_ADVANCED_FCB_HEADER  structure is a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, it is a stream control block (SCB).

If the file is used as a paging file, the FSRTL_ADVANCED_FCB_HEADER structure must be allocated from nonpaged pool. Otherwise, it can be allocated from paged or nonpaged pool.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>
</dt>
<dt>
<a href="ifsk.fsrtl_per_stream_context">FSRTL_PER_STREAM_CONTEXT</a>
</dt>
<dt>
<a href="ifsk.fsrtlaretherecurrentfilelocks">FsRtlAreThereCurrentFileLocks</a>
</dt>
<dt>
<a href="ifsk.fsrtlcopyread">FsRtlCopyRead</a>
</dt>
<dt>
<a href="ifsk.fsrtlcopywrite">FsRtlCopyWrite</a>
</dt>
<dt>
<a href="ifsk.fsrtlsetupadvancedheader">FsRtlSetupAdvancedHeader</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_COMMON_FCB_HEADER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
