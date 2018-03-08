# Experience API
## Advanced Distributed Learning (ADL) Co-Laboratories

>#### License

>"Copyright 2013 Advanced Distributed Learning (ADL) Initiative, U.S. Department of Defense

>Licensed under the Apache License, Version 2.0 (the "License"). You may not use this file except 
>in compliance with the License. You may obtain a copy of the License at
>http://www.apache.org/licenses/LICENSE-2.0

>Unless required by applicable law or agreed to in writing, software distributed under the License 
>is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express 
>or implied. See the License for the specific language governing permissions and limitations under 
>the License."

>This document was authored by members of the Experience API Working Group (see 
>list in [CONTRIBUTING.md](CONTRIBUTING.md#contributors)) in support of the Office of the Deputy Assistant Secretary of 
>Defense (Readiness) Advanced Distributed Learning (ADL) Initiative. Please 
>send all feedback and inquiries to helpdesk@adlnet.gov  

## Table of Contents
*	Part One:	[About the Experience API](./xAPI-About.md#partone)  
	*	1.0.	[Introduction](./xAPI-About.md#introduction-partone) 
	*	2.0.	[How To Use This Document](./xAPI-About.md#readingguidelines)  
		*	2.1.	[MUST / SHOULD / MAY](./xAPI-About.md#def-must-should-may)  
	 	*	2.2.	[Guidelines for Interpreting Descriptive Text and Tables](./xAPI-About.md#interpret-text-table)  
	*	3.0.	[Serialization and JavaScript Object Notation](./xAPI-About.md#json)
	*	4.0.	[Definitions](./xAPI-About.md#definitions) 
	*	5.0.	[xAPI Components](./xAPI-About.md#xapi-components) 
	*	6.0.	[Extending xAPI](./xAPI-About.md#extending-xapi) 
	*	7.0.	[Profiles and Communities of Practice](./xAPI-About.md#COPs)  
	*	[Appendices](./xAPI-About.md#append1)  
		*	[Appendix A: Revision History](./xAPI-About.md#Appendix1A)  
		*	[Appendix B: cmi5 Example](./xAPI-About.md#Appendix1B)  
*	Part Two:	[Experience API Data](./xAPI-Data.md#parttwo)  
	*	1.0.	[Documents](./xAPI-Data.md#documents) 
	*	2.0.	[Statements](./xAPI-Data.md#statements)  
		*	2.1.	[Purpose](./xAPI-Data.md#statement-purpose)  
	 	*	2.2.	[Formatting Requirements](./xAPI-Data.md#dataconstraints) 
	 	*	2.3.	[Statement Lifecycle](./xAPI-Data.md#lifecycle) 
		 	*	2.3.1.	[Statement Immutability](./xAPI-Data.md#statement-immutability-and-exceptions) 
		 	*	2.3.2.	[Voiding](./xAPI-Data.md#voided) 
   		*	2.4.	[Statement Properties](./xAPI-Data.md#statement-properties)  
	        *	2.4.1.	[ID](./xAPI-Data.md#stmtid)  
	        *	2.4.2.	[Actor](./xAPI-Data.md#actor)  
	        *	2.4.3.	[Verb](./xAPI-Data.md#verb)  
	        *	2.4.4.	[Object](./xAPI-Data.md#object)  
	        *	2.4.5.	[Result](./xAPI-Data.md#result)  
	        *	2.4.6.	[Context](./xAPI-Data.md#context)  
	        *	2.4.7.	[Timestamp](./xAPI-Data.md#timestamp)  
	        *	2.4.8.	[Stored](./xAPI-Data.md#stored)  
	        *	2.4.9.	[Authority](./xAPI-Data.md#authority)  
	        *	2.4.10.	[Version](./xAPI-Data.md#version)  
	        *	2.4.11.	[Attachments](./xAPI-Data.md#attachments)  
    	*	2.5.	[Retrieval of Statements](./xAPI-Data.md#retrieval)   
    	*	2.6.	[Signed Statements](./xAPI-Data.md#signature)  
	*	3.0.	[Metadata](./xAPI-Data.md#metadata)
		*	3.1.	[IRI Requirements](./xAPI-Data.md#iri-requirements)  
		*	3.2.	[Hosted Metadata](./xAPI-Data.md#miscmeta)  
    *	4.0.	[Special Data Types and Rules](./xAPI-Data.md#special-data)  
		*	4.1.	[Extensions](./xAPI-Data.md#miscext) 
		*	4.2.	[Language Maps](./xAPI-Data.md#lang-maps)
		*	4.3.	[IRIs](./xAPI-Data.md#iris)
		*	4.4.	[UUIDs](./xAPI-Data.md#uuids)
		*	4.5.	[ISO 8601 Timestamps](./xAPI-Data.md#timestamps)
		*	4.6.	[ISO 8601 Durations](./xAPI-Data.md#durations)
	*	[Appendices](./xAPI-Data.md#append2)  
		*	[Appendix A: Example Statements](./xAPI-Data.md#Appendix2A)  
		*	[Appendix B: Example statement objects of different types](./xAPI-Data.md#Appendix2B)  
		*	[Appendix C: Example definitions for Activities of type "cmi.interaction"](./xAPI-Data.md#Appendix2C)  	
		*	[Appendix D: Example Signed Statement](./xAPI-Data.md#Appendix2D)  
*	Part Three:	[Data Processing, Validation, and Security](./xAPI-Communication.md#partthree)  
	*	1.0.	[Requests](./xAPI-Communication.md#requests)
		*	1.1.	[HEAD Request Implementation](./xAPI-Communication.md#httphead)  
	 	*	1.2.	[Headers](./xAPI-Communication.md#headers) 
	 	*	1.3.	[Alternate Request Syntax](./xAPI-Communication.md#alt-request-syntax) 
	 	*	1.4.	[Encoding](./xAPI-Communication.md#encoding) 
	 	*	1.5.	[Content Types](./xAPI-Communication.md#content-types) 
	        *	1.5.1.	[Application/JSON](./xAPI-Communication.md#applicationjson) 
	        *	1.5.2.	[Multipart/Mixed](./xAPI-Communication.md#multipartmixed)
	*	2.0.	[Resources](./xAPI-Communication.md#datatransfer)   
	 	*	2.1.	[Statement Resource](./xAPI-Communication.md#stmtres) 
	 	*	2.2.	[Documents Resources](./xAPI-Communication.md#doctransfer) 
	 	*	2.3.	[State Resource](./xAPI-Communication.md#stateres) 
	 	*	2.4.	[Agents Resource](./xAPI-Communication.md#agentsres) 
	 	*	2.5.	[Activities Resource](./xAPI-Communication.md#activitiesres) 
	 	*	2.6.	[Agent Profile Resource](./xAPI-Communication.md#agentprofres) 
	 	*	2.7.	[Activity Profile Resource](./xAPI-Communication.md#actprofres) 
	 	*	2.8.	[About Resource](./xAPI-Communication.md#aboutresource) 
   	*	3.0.	[Data Validation](./xAPI-Communication.md#validation)     
    	*	3.1.	[Concurrency](./xAPI-Communication.md#concurrency)  
    	*	3.2.	[Error Codes](./xAPI-Communication.md#errorcodes)
    	*	3.3     [Versioning](./xAPI-Communication.md#versioning)  
    *	4.0.	[Authentication](./xAPI-Communication.md#authentication)  
		*	4.1.	[OAuth 1.0 Authentication Scenarios and Methods](./xAPI-Communication.md#authdefs) 
		*	4.2.	[OAuth 1.0 Authorization Scope](./xAPI-Communication.md#oauthscope)
    *	5.0	[Security](./xAPI-Communication.md#security)
	*	[Appendices](./xAPI-Communication.md#append3)  
		*	[Appendix A: Converting Statements to 1.0.0](./xAPI-Communication.md#Appendix3A)  
		*	[Appendix B: Table of All Resources](./xAPI-Communication.md#Appendix3B)  
		*	[Appendix C: Cross Domain Request Example](./xAPI-Communication.md#Appendix3C)  

<a name="partthree"></a>
# Part Three: Data Processing, Validation, and Security 

第三部分详细介绍Experience API的技术方面，涉及如何在学习记录提供者和LRS之间转换语句。一些库可用于处理这部分规范的各种技术（包括JavaScript）。因此，学习记录提供者可能没有必要充分理解这部分规范的每个细节。

<a name="requests"></a>

## <a name="1.0">1.0</a> Requests

xAPI跟踪是通过从学习记录提供者（客户端）到LRS（服务器）的HTTP请求完成的。本规范为本通信的某些方面提供了指导。如果没有提供指导，建议实施xAPI的人员使用当前的行业最佳实践。

<a name="httphead"></a>

### <a name="1.1">1.1</a> HEAD Request Implementation

###### <a name="1.1.s1"></a>Description
LRS响应PUT，POST，GET和DELETE请求的行为在下面的[资源](#resources) 中概述。所有支持GET请求的资源也都支持HEAD。LRS将通过仅使用HTTP头返回元信息来响应HEAD请求，而不是实际的文档。

###### <a name="1.1.s2"></a>Rationale

访问LRS的客户可能需要检查特定的陈述是否存在，或者确定文件的修改日期，例如State，Activity Profile或Agent Profile Resources中的文档。特别是对于大型文档，不检索整个文档只是为了检查其修改日期更有效。

###### <a name="1.1.s3"></a>LRS Requirements
* <a name="1.1.s3.b1"></a>The LRS MUST respond to any HTTP HEAD request as it would have responded to an otherwise
identical HTTP GET request except:
    * <a name="1.1.s3.b1.b1"></a>The message-body MUST be omitted.
    * <a name="1.1.s3.b1.b2"></a>The Content-Length header MAY be omitted, in order to avoid wasting LRS resources.

<a name="headers"></a> 

### <a name="1.2">1.2</a> Headers

##### <a name="1.2.s1"></a>Header Parameters
在xAPI数据传输中使用的某些标头参数是[标准HTTP标头](http://en.wikipedia.org/wiki/List_of_HTTP_header_fields)。其他则针对该规范。预计学习记录提供者将使用以下请求标题中的部分或全部类型的请求和本规范中描述的情况：

* <a name="1.2.s1.b1"></a>Accept
* <a name="1.2.s1.b2"></a>Accept-Encoding
* <a name="1.2.s1.b3"></a>Accept-Language
* <a name="1.2.s1.b4"></a>Authorization
* <a name="1.2.s1.b5"></a>Content-Type
* <a name="1.2.s1.b6"></a>Content-Length
* <a name="1.2.s1.b7"></a>Content-Transfer-Encoding
* <a name="1.2.s1.b8"></a>If-Match
* <a name="1.2.s1.b9"></a>If-None-Match
* <a name="1.2.s1.b10"></a>X-Experience-API-Version 

预计LRS将使用以下响应标头。再次，并非所有这些适用于每种类型的请求和/或情况：

* <a name="1.2.s1.b11"></a>Content-Type
* <a name="1.2.s1.b12"></a>Content-Length
* <a name="1.2.s1.b13"></a>Last-Modified
* <a name="1.2.s1.b14"></a>ETag
* <a name="1.2.s1.b15"></a>Status
* <a name="1.2.s1.b16"></a>X-Experience-API-Version
* <a name="1.2.s1.b17"></a>X-Experience-API-Consistent-Through

以上列表并不打算详尽无遗。有关详细信息，请参阅本文档中的要求。

<a name="alt-request-syntax"></a>

### <a name="1.3">1.3</a> Alternate Request Syntax


###### <a name="1.3.s1"></a>Description

xAPI的目标之一是允许跨域跟踪，即使xAPI试图启用除浏览器以外的应用程序的跟踪，仍然需要支持浏览器。例如，Internet Explorer 8和9不实现跨源资源共享，而是使用自己的跨域请求API，由于仅支持“GET”和“POST”，因此不能使用上述所有的xAPI，而不支持允许设置HTTP标头。

###### <a name="1.3.s2"></a>Details/Requirements

以下描述了仅在由于上述限制而无法使用特定呼叫的通常语法时才使用的备用语法。由于查询字符串长度的限制，此备用语法也可用于GET语句。

See [Appendix C: Cross Domain Request Example](#Appendix3C) for an example. 

###### <a name="1.3.s3"></a>Requirements

__Method__:  
* <a name="1.3.s3.b1"></a>All xAPI requests issued MUST be POST. 
* <a name="1.3.s3.b2"></a>The intended xAPI method MUST be included as the value of the "method" query 
string parameter. 
* <a name="1.3.s3.b3"></a>The Learning Record Provider MUST NOT include any other query string parameters on the request.

Example: http://example.com/xAPI/statements?method=PUT  

__Content__:  
* <a name="1.3.s3.b4"></a>If the xAPI call involved sending content, the Learning Record Provider MUST URL encode that content and 
include it as a form parameter called "content". 
* <a name="1.3.s3.b5"></a>The LRS MUST interpret this content as a UTF-8 string. Storing binary data is not supported with this syntax.  

__Headers__:  
* <a name="1.3.s3.b6"></a>The Learning Record Provider MAY include any header parameters required by this specification which are 
expected to appear in the HTTP header as form parameters with the same names. This applies 
to the following parameters: Authorization, X-Experience-API-Version, Content-Type, Content-Length,
If-Match and If-None-Match. It does not apply to Content-Transfer-Encoding.
* <a name="1.3.s3.b7"></a>The LRS MUST treat the form parameters listed above as header parameters. 
* <a name="1.3.s3.b8"></a>The Learning Record Provider MUST include other header parameters not listed above in the HTTP header as normal. 
* <a name="1.3.s3.b9"></a>The Learning Record Provider SHOULD* still include a Content-Type header (in the HTTP header) for this type of 
request with a value of 'application/x-www-form-urlencoded'. 
* <a name="1.3.s3.b10"></a>The Content-Type form parameter SHOULD* specify the content type of the content within the content form parameter. 
* <a name="1.3.s3.b11"></a>The Learning Record Provider SHOULD* still include a Content-Length header (in the HTTP header) for this type of 
request indicating the overall length of the request's content. 
* <a name="1.3.s3.b12"></a>The Content-Length form parameter SHOULD* specify the length of the content within the 
content form parameter and will therefore be a lower figure than the length listed in the Content-Length header. 

__Query string parameters__:  
* <a name="1.3.s3.b13"></a>Any query string parameters other than "method" MUST instead be included as a form parameter 
with the same name. 
* <a name="1.3.s3.b14"></a>The LRS MUST treat any form parameters other than "content" or the header parameters 
listed above as query string parameters. 

__Attachments__: Note that due to issues relating to encoding, it is not possible to send 
binary data attachments using this syntax. See [Attachments](./xAPI-Data.md#attachments) 

* <a name="1.3.s3.b15"></a>The LRS MUST support the syntax above.  

There might be cases where there is a requirement for the Learning Record Provider to support applications or browsers where the 
Client code is hosted on a different scheme (HTTP or HTTPS) from the LRS. A proxy is only needed IF you want to support HTTP to 
HTTPS requests from IE 9 or lower. You can do HTTP to HTTPS (or HTTPS to HTTP!) without a proxy if you use a modern browser. 
Two simple solutions might be to 1) set up a proxy pass through on the same scheme as the Client code to the LRS or 2) to host an 
intermediary server-side LRS on the same scheme as the Client code to route Statements to the target LRS.

Strongly consider security risks before making the decision to use implementations that use HTTP.

<a name="encoding"></a> 

### <a name="1.4">1.4</a> Encoding

###### <a name="1.4.s1"></a>Requirements
* <a name="1.4.s1.b1"></a>All strings MUST be encoded and interpreted as UTF-8. 

<a name="content-types"></a> 
### <a name="1.5">1.5</a> Content Types
Requests and responses within this specification normally use an `application/json` content type. Exceptions to this are:

* <a name="1.5.b1"></a>Documents can have any content type. 
* <a name="1.5.b2"></a>Statement requests that can sometimes include Attachments use the `multipart/mixed` content type. 

<a name="applicationjson"></a> 
#### <a name="1.5.1">1.5.1</a> Application/JSON
Requests within this specification normally use an `application/json` content type. 

###### <a name="1.5.1.s1"></a>LRS Requirements
* <a name="1.5.1.s1.b1"></a>When receiving a PUT or POST with a document type of `application/json`, an LRS MUST accept batches 
of Statements which contain no Attachment Objects.
* <a name="1.5.1.s1.b2"></a>When receiving a PUT or POST with a document type of `application/json`, an LRS MUST accept batches 
of Statements which contain only Attachment Objects with a populated fileUrl.

<a name="multipartmixed"></a> 
#### <a name="1.5.2">1.5.2</a> Multipart/Mixed

The `multipart/mixed` content type is used for requests that *could* include Attachments. This does not mean that all 
"multipart/mixed" requests necessarily do include Attachments.

##### <a name="1.5.2.s1"></a>Procedure For The Exchange Of Attachments

* <a name="1.5.2.s1.b1"></a>A Statement request including zero or more Attachments is construed as described below.

* <a name="1.5.2.s1.b2"></a>The Statement is sent using a Content-Type of `multipart/mixed`. Any Attachments are placed 
at the end of such transmissions.

* <a name="1.5.2.s1.b3"></a>The LRS decides whether to accept or reject the Statement based on the information in the first part.

* <a name="1.5.2.s1.b4"></a>If it accepts the request, it can match the raw data of an Attachment(s) with the 
Attachment header by comparing the SHA-2 of the raw data to the SHA-2 declared in the header. It MUST not do so any other way.

###### <a name="1.5.2.s2"></a>Requirements for Attachment Statement Batches

A request transmitting a Statement batch, Statement results, or single Statement that includes Attachments MUST satisfy one of the 
following criteria:

* <a name="1.5.2.s2.b1"></a>It MUST be of type `application/json` and include a fileUrl for every Attachment EXCEPT for Statement 
results when the "attachments" filter is `false`.
* <a name="1.5.2.s2.b2"></a>It MUST conform to the definition of "multipart/mixed" in [RFC 2046](https://www.ietf.org/rfc/rfc2046.txt) and:
    * <a name="1.5.2.s2.b2.b1"></a>The first part of the multipart document MUST contain the Statements themselves, 
    with type `application/json`.
    * <a name="1.5.2.s2.b2.b2"></a>Each additional part contains the raw data for an Attachment and forms a logical 
    part of the Statement. This capability will be available when issuing PUT or POST requests against the Statement Resource.
    * <a name="1.5.2.s2.b2.b3"></a>MUST include an X-Experience-API-Hash parameter in each part's header after the 
    first (Statements) part.
    * <a name="1.5.2.s2.b2.b4"></a>MUST include a Content-Transfer-Encoding parameter with a value of `binary` in each 
    part's header after the first (Statements) part.
    * <a name="1.5.2.s2.b2.b5"></a>SHOULD only include one copy of an Attachment's data when the same Attachment is used 
    in multiple Statements that are sent together.
    * <a name="1.5.2.s2.b2.b6"></a>SHOULD include a Content-Type parameter in each part's header. For the first part 
    (containing the Statement) this MUST be `application/json`.
   	* <a name="1.5.2.s2.b2.b7"></a>Where parameters have a corresponding property within the attachment Object 
   	(outlined in the table above), and both the parameter and property are specified for a given Attachment, 
	the value of these parameters and properties MUST match. 

###### <a name="1.5.2.s3"></a>LRS Requirements

* <a name="1.5.2.s3.b1"></a>An LRS MUST include Attachments in the Transmission Format described above
when requested by the Client (see [Statement Resource](#stmtres)).
* <a name="1.5.2.s3.b2"></a>An LRS MUST NOT pull Statements from another LRS without requesting Attachments.
* <a name="1.5.2.s3.b3"></a>An LRS MUST NOT push Statements into another LRS without including Attachment data
received, if any, for those Attachments.
* <a name="1.5.2.s3.b4"></a>When receiving a PUT or POST with a document type of `multipart/mixed`, an LRS MUST accept batches of 
Statements that contain Attachments in the Transmission Format described above.
* <a name="1.5.2.s3.b5"></a>When receiving a PUT or POST with a document type of `multipart/mixed`, an LRS MUST reject batches of 
Statements having Attachments that neither contain a fileUrl nor match a received Attachment part based on their hash.
* <a name="1.5.2.s3.b6"></a>When receiving a PUT or POST with a document type of `multipart/mixed`, an LRS SHOULD assume a 
Content-Transfer-Encoding of binary for Attachment parts.
* <a name="1.5.2.s3.b7"></a>An LRS MAY reject (batches of) Statements that are larger than the LRS is configured to allow.
* <a name="1.5.2.s3.b8"></a>When receiving a PUT or POST with a document type of `multipart/mixed`, an LRS SHOULD* accept batches 
of Statements which contain no Attachment Objects.
* <a name="1.5.2.s3.b9"></a>When receiving a PUT or POST with a document type of `multipart/mixed`, an LRS SHOULD* accept batches 
of Statements which contain only Attachment Objects with a populated fileUrl.

__Note:__ There is no requirement that Statement batches using the "mime/multipart" format contain Attachments.

###### <a name="1.5.2.s4"></a>Learning Record Provider Requirements

* <a name="1.5.2.s4.b1"></a>A Learning Record Provider MAY send Statements with Attachments as described above.
* <a name="1.5.2.s4.b2"></a>A Learning Record Provider MAY send multiple Statements where some or all have 
Attachments if using POST.
* <a name="1.5.2.s4.b3"></a>A Learning Record Provider MAY send batches of type `application/json` where every attachment
Object has a fileUrl, ignoring all requirements based on the "multipart/mixed" format.
* <a name="1.5.2.s4.b4"></a>A Learning Record Provider SHOULD use SHA-256, SHA-384, or SHA-512 to populate the "sha2" property.

###### <a name="1.5.2.s5"></a>File URL
文件URL旨在提供可以从中接收附件的位置。但是，附件所有者没有要求无限期地在附件中提供附件数据，或者没有安全限制地使附件公开可用。在确定附件托管安排时，鼓励使用“fileUrl”属性创建声明的人考虑声明最终收件人的需求，特别是如果附件内容未包含在声明中。

* <a name="1.5.2.s5.b1"></a>The Attachment data SHOULD be retrievable at the URL indicated by the fileUrl.
* <a name="1.5.2.s5.b2"></a>The owner of the attachment MAY stop providing the attachment data at this IRL at any time. 
* <a name="1.5.2.s5.b3"></a>Security restrictions MAY be applied to those attempting to access the Attachment data at this IRL. 

附件可供使用的时间以及适用于托管附件的安全限制超出了本规范的范围。

###### <a name="1.5.2.s6"></a>Example

Below is an example of a very simple Statement with an Attachment. Please note the following:

* <a name="1.5.2.s6.b1"></a>The boundary in the sample was chosen to demonstrate valid character classes;
* <a name="1.5.2.s6.b2"></a>The selected boundary does not appear in any of the parts;
* <a name="1.5.2.s6.b3"></a>For readability the sample attachment is of type "text/plain". Even if it had been 
a binary type like "image/jpeg", no encoding would be done, the raw octets would be included;
* <a name="1.5.2.s6.b4"></a>Per RFC 2046, the boundary is `<CRLF>` followed by -- followed by the boundary string 
declared in the header.

**注意：**在创建或解析这些消息时不要忘了 ```<CRLF>``` 。

Headers:

``` 
Content-Type: multipart/mixed; boundary="abcABC0123'()+_,-./:=?"
X-Experience-API-Version:1.0.0
```
Content:
```

--abcABC0123'()+_,-./:=?
Content-Type:application/json

{
    "actor": {
        "mbox": "mailto:sample.agent@example.com",
        "name": "Sample Agent",
        "objectType": "Agent"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/answered",
        "display": {
            "en-US": "answered"
        }
    },
    "object": {
        "id": "http://www.example.com/tincan/activities/multipart",
        "objectType": "Activity",
        "definition": {
            "name": {
                "en-US": "Multi Part Activity"
            },
            "description": {
                "en-US": "Multi Part Activity Description"
            }
        }
    },
    "attachments": [
        {
            "usageType": "http://example.com/attachment-usage/test",
            "display": { "en-US": "A test attachment" },
            "description": { "en-US": "A test attachment (description)" },
            "contentType": "text/plain; charset=ascii",
            "length": 27,
            "sha2": "495395e777cd98da653df9615d09c0fd6bb2f8d4788394cd53c56a3bfdcd848a"
        }
    ]
}
--abcABC0123'()+_,-./:=?
Content-Type:text/plain
Content-Transfer-Encoding:binary
X-Experience-API-Hash:495395e777cd98da653df9615d09c0fd6bb2f8d4788394cd53c56a3bfdcd848a

here is a simple attachment
--abcABC0123'()+_,-./:=?--
```

<a name="datatransfer"></a> <a name="resources"></a>
## <a name="2.0">2.0</a> Resources

LRS 通过 RESTful HTTP 方法与本节中概述的资源进行交互。语句资源可以用于跟踪学习记录。其他资源提供附加功能。

LRS将支持本节中描述的所有资源。对于不是LRS的工具，也可以选择遵循本节所述的一种或多种资源和方法的LRS要求。例如，为了接收由LRS转发的传入语句，工具可能实现POST语句。这样一个系统不被认为是LRS或“部分LRS”。它根本不是一个LRS。

__Note:__ In all of the example endpoints where xAPI resources are located given in the specification, `http://example.com/xAPI/` 
is the example base endpoint of the LRS. All other IRI syntax after this represents the particular resource used. 
A full list of the endpoints is included in [Appendix B: Table of All Resources](#Appendix3B).
**注意：**在规范中给出xAPI资源所在的所有示例端点中，http：// example.com / xAPI /

在规范中给出xAPI资源所在的所有示例端点中，http：// example.com / xAPI /
是LRS的示例基本端点。之后的所有其他IRI语法代表所使用的特定资源。 [附录B：所有资源表](#Appendix3B)包含了完整的端点列表。

###### <a name="2.0.s1"></a>Requirements

* <a name="2.0.s1.b1"></a>The LRS MUST support all of the resources described in this section. 
* <a name="2.0.s1.b2"></a>If the LRS implements OAuth 1.0, the LRS MUST also support all of the OAuth resources 
described in [OAuth Authorization Scope](#oauthscope).
* <a name="2.0.s1.b3"></a>The LRS MAY support additional resources not described in this specification. 
* <a name="2.0.s1.b4"></a>Past, current and future versions of this specification do not and will not define endpoints 
with path segments starting with `extensions/`. LRSs supporting additional resources not defined in this specification SHOULD 
define their endpoints with path segments starting with `extensions/`.

<a name="stmtres"></a> 

#### <a name="2.1">2.1</a> Statement Resource

###### <a name="2.1.s1"></a>Description

The basic communication mechanism of the Experience API.  

<a name="stmtresput"></a>

#### <a name="2.1.1">2.1.1</a> PUT Statements

###### <a name="2.1.1.s1"></a>Details

Example endpoint: `http://example.com/xAPI/statements`

Stores a single Statement with the given id. POST can also be used to store single Statements.

**Content:** The Statement object to be stored. 

**Returns:** `204 No Content`  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Default</th><th>Description</th><th>Required</th></tr>
	<tr id="2.1.1.s1.table1.row1"><td>statementId</td><td>String</td><td> 
	<td>Id of Statement to record</td></td><td>Required</td></tr>
</table>

###### <a name="2.1.1.s2"></a>LRS Requirements

* <a name="2.1.1.s2.b1"></a>The LRS MAY respond before Statements that have been stored are available for retrieval.

* <a name="2.1.1.s2.b2"></a>An LRS MUST NOT make any modifications to its state based on receiving a Statement
with a statementId that it already has a Statement for. Whether it responds with `409 Conflict` or `204 No Content`, 
it MUST NOT modify the Statement or any other Object.

* <a name="2.1.1.s2.b3"></a>If the LRS receives a Statement with an id it already has a Statement for, it SHOULD
verify the received Statement matches the existing one and SHOULD return `409 Conflict` if they
do not match. See [Statement comparison requirements](./xAPI-Data.md#statement-comparison-requirements).

* <a name="2.1.1.s2.b4"></a>If the LRS receives a batch of Statements containing two or more Statements with the same id, 
it SHOULD* reject the batch and return `400 Bad Request`.



###### <a name="2.1.1.s3"></a>Learning Record Provider Requirements

* <a name="2.1.1.s3.b1"></a>Learning Record Providers SHOULD POST Statements including the Statement "id" property 
instead of using PUT. 
* <a name="2.1.1.s3.b2"></a>When PUTing Statements, the "id" property of the Statement SHOULD be used. 
* <a name="2.1.1.s3.b3"></a>Where provided, the "id" property of the Statement MUST match the "statementId" parameter of the request. 

<a name="stmtrespost"></a>

#### <a name="2.1.2">2.1.2</a> POST Statements

###### <a name="2.1.2.s1"></a>Details

Example endpoint: `http://example.com/xAPI/statements`

Stores a Statement, or a set of Statements.

**Content:** An array of Statements or a single Statement to be stored. 

**Returns:** `200 OK`, Array of Statement id(s) (UUID) in the same order as the corresponding stored Statements.  

###### <a name="2.1.2.s2"></a>Requirements

* <a name="2.1.2.s2.b1"></a>The LRS MAY respond before Statements that have been stored are available for retrieval.
* <a name="2.1.2.s2.b2"></a>GET Statements MAY be called using POST and form parameters if necessary as query strings 
have limits. See [Alternate Request Syntax](#alt-request-syntax) for more details.
* <a name="2.1.2.s2.b3"></a>The LRS MUST differentiate a POST to add a Statement or to list Statements based on the 
parameters passed. See [Alternate Request Syntax](#alt-request-syntax) for more details.
* <a name="2.1.2.s2.b4"></a>An LRS MUST NOT make any modifications to its state based on receiving a Statement
with an id that it already has a Statement for. Whether it responds with `409 Conflict` or `204 No Content`, 
it MUST NOT modify the Statement or any other Object.
* <a name="2.1.2.s2.b5"></a>If the LRS receives a Statement with an id it already has a Statement for, it SHOULD
verify the received Statement matches the existing one and SHOULD return `409 Conflict` if they
do not match. See [Statement comparison requirements](./xAPI-Data.md#statement-comparison-requirements).
* <a name="2.1.2.s2.b6"></a>If the LRS receives a batch of Statements containing two or more Statements with the same id, 
it SHOULD* reject the batch and return `400 Bad Request`.

<a name="stmtresget"></a>

#### <a name="2.1.3">2.1.3</a> GET Statements

###### <a name="2.1.3.s1"></a>Details

Example endpoint: `http://example.com/xAPI/statements`

调用此方法来获取单个Statement或多个Statements。如果指定了statementId或voidedStatementId参数，则返回单个Statement。

否则返回：A [StatementResult]（./ xAPI-Data.md＃retrieval）对象，一个基于“存储”时间的反向时间顺序的语句列表，取决于权限和最大列表长度。如果有其他结果可用，则用于检索它们的IRL将包含在StatementResult对象中。

**Content:** None.

**Returns:** `200 OK`, Statement or [Statement Result](./xAPI-Data.md#retrieval)

<table>
	<tr><th>Parameter</th><th>Type</th><th>Default</th><th>Description</th><th>Required</th></tr>
	<tr id="2.1.3.s1.table1.row1">
		<td>statementId</td>
		<td>String</td>
		<td> </td>
		<td>Id of Statement to fetch</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row2">
		<td>voidedStatementId</td>
		<td>String</td>
		<td> </td>
		<td>Id of voided Statement to fetch. see <a href="./xAPI-Data.md#voided">Voided
		Statements</a></td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row3">
		<td>agent</td>
		<td>Agent or Identified Group Object (JSON)</td>
		<td> </td>
		<td>Filter, only return Statements for which the specified Agent or Group is 
		the Actor or Object of the Statement.
			<ul>
				<li> 
					Agents or Identified Groups are equal when the same 
					Inverse Functional Identifier is used in each Object compared and 
					those Inverse Functional Identifiers have equal values.
				</li><li>
					For the purposes of this filter, Groups that have members 
					which match the specified Agent	based on their Inverse Functional
					Identifier as described above are considered a match
				</li>
			</ul>
			<br><br>See <a href="./xAPI-Data.md#actor">agent/group</a> Object definition
			for details.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row4">
		<td>verb</td>
		<td>Verb id (IRI)</td>
		<td> </td>
		<td>Filter, only return Statements matching the specified Verb id.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row5">
		<td>activity</td>
		<td>Activity id (IRI)</td>
		<td> </td>
		<td>
			Filter, only return Statements for which the Object of the Statement is 
			an Activity with the specified id.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row6">
		<td>registration</td>
		<td>UUID</td>
		<td> </td>
		<td>
			Filter, only return Statements matching the specified registration 
			id. Note that although frequently a unique registration will be used 
			for one Actor assigned to one Activity, this cannot be assumed. 
			If only Statements for a certain Actor or Activity are required, 
			those parameters also need to be specified.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row7">
	<td>related_activities</td>
		<td>Boolean</td>
		<td>false</td>
		<td>
			Apply the Activity filter broadly. Include Statements for which the Object,
			any of the  context Activities, or any of those properties in a contained
			SubStatement match the Activity parameter, instead of that parameter's 
			normal behavior. Matching is defined in the same way it is for the 
			"activity" parameter.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row8">
		<td>related_agents</td>
		<td>Boolean</td>
		<td>false</td>
		<td>
			Apply the Agent filter broadly. Include Statements for which 
			the Actor, Object, Authority, Instructor, Team,
			or any of these properties in a contained SubStatement match the Agent parameter,
			instead of that parameter's normal behavior. Matching is defined in the same way
			it is for the "agent" parameter.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row9">
		<td>since</td>
		<td>Timestamp</td>
		<td> </td>
		<td>Only Statements stored since the specified Timestamp (exclusive) are returned.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row10">
		<td>until</td>
		<td>Timestamp</td>
		<td> </td>
		<td>Only Statements stored at or before the specified Timestamp are returned.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row11">
		<td>limit</td>
		<td>Nonnegative Integer</td>
		<td>0</td>
		<td>
			Maximum number of Statements to return. 0 indicates return the 
			maximum the server will allow.
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row12">
		<td>format</td>
		<td>String: (<code>ids</code>, <code>exact</code>, or <code>canonical</code>)</td>
		<td>exact</td>
		<td>If <code>ids</code>, only include minimum information necessary in Agent, Activity, Verb 
			and Group Objects to identify them. For Anonymous Groups this means including 
			the minimum information needed to identify each member. 
			<br/><br/>
			If <code>exact</code>, return Agent, Activity, Verb and Group Objects populated exactly as they 
			were when the Statement was received. An LRS requesting Statements for the purpose 
			of importing them would use a format of "exact" in order to maintain 
			<a href="./xAPI-Data.md#statement-immutability-and-exceptions">Statement Immutability</a>.  
			<br/><br/>
			If <code>canonical</code>, return Activity Objects and Verbs populated with the canonical
			definition of the Activity Objects and Display of the Verbs as determined by the LRS, after
			applying the <a href="#queryLangFiltering">language filtering process defined below</a>,
			and return the original Agent and Group Objects as in "exact" mode.  
		</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row13">
		<td>attachments</td><td>Boolean</td><td>false</td>
		<td>If <code>true</code>, the LRS uses the multipart response format and includes all attachments as 
		described previously.  If <code>false</code>, the LRS sends the prescribed response with Content-Type 
		application/json and does not send attachment data.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.1.3.s1.table1.row14">
		<td>ascending</td>
		<td>Boolean</td>
		<td>false</td>
		<td>If <code>true</code>, return results in ascending order of stored time</td>
		<td>Optional</td>
	</tr>
</table>

**注意：**在 JSON 中，布尔类型参数的值应当表示为 `true` 或 `false`。
###### <a name="2.1.3.s2"></a>Requirements

* <a name="2.1.3.s2.b1"></a>The LRS MUST reject with a `400 Bad Request` error any requests to this resource 
which contain both statementId and voidedStatementId parameters

* <a name="2.1.3.s2.b2"></a>The LRS MUST reject with an `400 Bad Request` error any requests to this resource which 
contain statementId or voidedStatementId parameters, and also contain any other parameter besides "attachments" or "format".

* <a name="2.1.3.s2.b3"></a>The LRS MAY apply additional query filter criteria based on permissions associated
with the credentials used. 

* <a name="2.1.3.s2.b4"></a>In the event that no Statements are found matching the query filter criteria, the LRS MUST still return 
`200 OK` and a [StatementResult](./xAPI-Data.md#retrieval) Object. In this case, the "statements" property will contain an empty array.

* <a name="2.1.3.s2.b5"></a>The LRS MUST include the header "X-Experience-API-Consistent-Through", in 
[ISO 8601 combined date and time](https://en.wikipedia.org/wiki/ISO_8601#Combined_date_and_time_representations) format, 
on all responses to Statements Resource requests, with a value of the timestamp for which all Statements that have or will have a 
"stored" property before that time are known with reasonable certainty to be available for retrieval. This time SHOULD take 
into account any temporary condition, such as excessive load, which might cause a delay in Statements becoming available 
for retrieval. It is expected that this will be a recent timestamp, even if there are no recently received Statements. 

* <a name="2.1.3.s2.b6"></a>If the "attachment" property of a GET Statement is used and is set to `true`, the LRS MUST 
use the multipart response format and include all Attachments as described in [Part Two](./xAPI-Data.md#attachments).

* <a name="2.1.3.s2.b7"></a>If the "attachment" property of a GET statement is used and is set to `false`, the LRS MUST NOT
include Attachment raw data and MUST report `application/json`.

* <a name="2.1.3.s2.b8"></a>The LRS SHOULD* include a "Last-Modified" header which matches the "stored" Timestamp 
of the Statement. 

<a name="queryStatementRef"></a>

###### <a name="2.1.3.s3"></a>Filter Conditions for StatementRefs

本节概述了针对其他语句的语句有时会被视为符合查询的过滤条件的规则，即使它们与原始查询的过滤参数不匹配。当使用“statementId”或“voidedStatementId”查询参数检索单个Statement时，这些规则**不适用**。

“定位语句”表示一个语句（定位语句）包含另一个语句（定位语句）的语句ID作为语句参考作为语句的对象。

对于不是基于时间或序列（即“since”，“until”或“limit”）以外的过滤器参数，以另一个语句为目标的语句（通过使用StatementRef作为语句的对象）将符合如果目标语句符合过滤条件，则为过滤条件。

基于时间和序列的参数必须仍然以这种方式应用于Statement Statement的Statement。该规则递归地应用，以便当针对c和上述过滤条件的目标b匹配“语句c”时，“语句a”是匹配的。

For example, consider the Statement 'Ben passed explosives training', and a follow up
Statement: "Andrew confirmed <StatementRef to original Statement\>". The follow up
Statement will not mention 'Ben' or 'explosives training', but when fetching Statements
with an Actor filter of 'Ben' or an Activity filter of 'explosives training', both
Statements match and will be returned so long as they fall into the time or sequence
being fetched.

例如，考虑“Ben passed explosives training”声明和后续声明：“Andrew confirmed <StatementRef to Original Statement \>”。后续声明不会提及'Ben'或'explosives training'，但是当获得'Ben'的Actor过滤器或'explosives training'的活动过滤器时，两个语句匹配并且只要它们落下就会被返回进入被提取的时间或顺序。

**注意：**在上下文中声明参考使用“Statement”性质的值不会影响声明的筛选。

<a name="queryLangFiltering"></a>

###### <a name="2.1.3.s4"></a>Language Filtering Requirements for Canonical Format Statements

* <a name="2.1.3.s4.b1"></a>Activity Objects contain Language Map Objects within their "name", "description" and various 
interaction components. The LRS MUST return only one language in each of these maps. 

* <a name="2.1.3.s4.b2"></a>The LRS MAY maintain canonical versions of language maps against any IRI identifying an object containing
language maps. This includes the language map stored in the Verb's "display" property and potentially some 
language maps used within extensions. 

* <a name="2.1.3.s4.b3"></a>If the LRS maintains a canonical version of a language map, it SHOULD* return this canonical language map
 when canonical format is used to retrieve Statements. 

* <a name="2.1.3.s4.b4"></a>The LRS SHOULD* return only one language within each language map for which it returns a canonical map. 

* <a name="2.1.3.s4.b5"></a>In order to choose the most relevant language, the LRS MUST apply the "Accept-Language" header as 
described in [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) 
(HTTP 1.1), except that this logic MUST be applied to each language map individually to select 
which language entry to include, rather than to the resource (list of Statements) as a whole.

<a name="voidedStatements"></a>

##### <a name="2.1.4">2.1.4</a> Voided Statements

[第二部分](./xAPI-Data.md#voided)描述了可以使语句无效的过程。本节介绍查询时如何处理无效声明。

客户可以根据无效声明的目标确定任何无效声明的存在和声明ID。除调试工具外，许多学习记录消费者不希望向用户显示无效声明，也不会将这些声明显示为活动流和其他报告的一部分。

###### <a name="2.1.4.s1"></a>Requirements

* <a name="2.1.4.s1.b1"></a>The LRS MUST not return any Statement which has been voided, unless that Statement has been 
requested by voidedStatementId. The process described in [the section on filter conditions for StatementRefs](#queryStatementRef) 
is no exception to this requirement. The process of retrieving voiding Statements is to request each 
individually by voidedStatementId.

* <a name="2.1.4.s1.b2"></a>The LRS MUST still return any Statements targeting the voided Statement, following the process 
and conditions described in [the section on filter conditions for StatementRefs](#queryStatementRef). This includes the 
voiding Statement, which cannot be voided. 

<a name="doctransfer"></a>

### <a name="2.2">2.2</a> Document Resources 

##### <a name="2.2.s1"></a>Description
Experience API为学习记录提供者提供了一种工具，用于以文档形式保存任意数据，可能与活动，代理或两者的组合有关。

##### <a name="2.2.s2"></a>Details
请注意，下表显示了泛型属性，而不是本规范中许多其他表的JSON对象。 id存储在IRL中，“updated”是HTTP头信息，而“contents”是HTTP文件本身（而不是Object）。
<table>
	<tr><th>Property</th><th>Type</th><th>Description</th></tr>
	<tr id="2.2.s2.table1.row1"><td>id</td><td>String</td><td>Set by Learning Record Provider, unique within the scope 
	of the Agent or Activity.</td></tr>
	<tr id="2.2.s2.table1.row2"><td>updated</td><td>Timestamp</td><td>When the document was most recently modified.</td></tr>
	<tr id="2.2.s2.table1.row3"><td>contents</td><td>Arbitrary binary data</td><td>The contents of the document</td></tr>
</table>


这三个文档资源提供了[文档](./xAPI-Data.md#documents)存储。每个资源的详细信息可在以下部分找到，本节中的信息适用于所有三种资源。

###### <a name="2.2.s3"></a>Details

<table>
	<tr>
		<th>Resource</th>
		<th>Method</th>
		<th>Endpoint</th>
		<th>Example</th>
	</tr>
	<tr id="2.2.s3.table1.row1">
		<td>State Resource</td>
		<td>POST</td>
		<td>activities/state</td>
		<td>http://example.com/xAPI/activities/state</td>
	</tr>
	<tr id="2.2.s3.table1.row2">
		<td>Activity Profile Resource</td>
		<td>POST</td>
		<td>activities/profile</td>
		<td>http://example.com/xAPI/activities/profile</td>
	</tr>
	<tr id="2.2.s3.table1.row3">
		<td>Agent Profile Resource</td>
		<td>POST</td>
		<td>agents/profile</td>
		<td>http://example.com/xAPI/agents/profile</td>
	</tr>
</table>

###### <a name="2.2.s4"></a>Requirements

* <a name="2.2.s4.b1"></a>A Learning Record Provider MAY send documents to any of the Document Resources for Activities and 
Agents that the LRS does not have prior knowledge of. 

* <a name="2.2.s4.b2"></a>The LRS MUST NOT reject documents on the basis of not having prior knowledge of the Activity and/or Agent.

##### <a name="2.2.s5"></a>Last Modified
The "Last Modified" header is set by the LRS when returning single or multiple documents in response to a GET request. 

###### <a name="2.2.s6"></a>Requirements
* <a name="2.2.s6.b1"></a>When returning a single document, the LRS SHOULD* include a "Last-Modified" header indicating when
the document was last modified. 
* <a name="2.2.s6.b2"></a>When returning multiple documents, the LRS SHOULD* include a "Last-Modified" header indicating when
the most recently modified document was last modified. 

###### <a name="2.2.s7"></a>JSON Procedure with Requirements

如果学习记录提供程序将变量作为JSON对象存储在内容类型为“application / json”的文档中，则可以使用POST将它们作为变量组来操作。

以下流程遍历该流程和流程要求。例如，一个文件包含：
```
{
	"x" : "foo",
	"y" : "bar"
}
```  
当一个LRS接收到一个内容类型为 `application/json` 的 POST 请求时，它也是一个内容类型为 `application/json` 的现有文档，它必须合并该已发布文档和现有文档。在这种情况下，合并定义为：
* <a name="2.2.s7.b1"></a>de-serialize the Objects represented by each document.
* <a name="2.2.s7.b2"></a>for each property directly defined on the Object being posted, set the corresponding
property on the existing Object equal to the value from the posted Object.    
* <a name="2.2.s7.b3"></a>store any valid json serialization of the existing Object as the document referenced in the request.

请注意，即使顶级属性是 Object，也只有顶级属性才会合并。每个原有属性的全部内容将被每个新属性的全部内容所取代。

例如，此文档的上传与上面现有文档的ID相同：

```
{
	"x" : "bash",
	"z" : "faz"
}
```  
存储在LRS中的结果文档是：
```
{
	"x" : "bash",
	"y" : "bar",
	"z" : "faz"
}
```

###### <a name="2.2.s8"></a>Requirements

* <a name="2.2.s8.b1"></a>If the document being posted or any existing document does not have a Content-Type
of `application/json`, or if either document cannot be parsed as a JSON Object, the LRS MUST
respond with HTTP status code `400 Bad Request`, and MUST NOT update the target document
as a result of the request.

* <a name="2.2.s8.b2"></a>If the merge is successful, the LRS MUST respond with HTTP status code `204 No Content`.

* <a name="2.2.s8.b3"></a>If a Learning Record Provider needs to delete a property, it SHOULD use a PUT request to replace 
the whole document as described below. 

<a name="stateres"></a> 

### <a name="2.3">2.3</a> State Resource

##### <a name="2.3.s1"></a>Description

通常，这是学习记录提供程序的暂存区域，它们没有自己的内部存储器，或者需要跨设备保持状态。

##### <a name="2.3.s2"></a>Details

调用的语义由“stateId”参数驱动。如果包含它，则GET和DELETE方法将对由 “stateId” 标识的单个定义的状态文档起作用。否则，GET将返回可用的 id，DELETE 将删除通过其他参数给定的上下文中的所有状态。该资源具有与其关联的[并发](#concurrency) 控件。

###### <a name="2.3.s3"></a>Single Document (PUT | POST | GET | DELETE)

Example endpoint: http://example.com/xAPI/activities/state

存储，更改，提取或删除指定活动，代理和注册（如果指定）上下文中存在的给定“stateId”指定的文档。

**Content (PUT | POST):** The document to be stored or updated.  
**Content (GET | DELETE):** None.  

**Returns (PUT | POST | DELETE):** `204 No Content`  
**Returns (GET):** `200 OK`, the State document 
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.3.s3.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s3.table1.row2">
		<td>agent</td>
		<td>Agent Object (JSON)</td>
		<td>The Agent associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s3.table1.row3">
		<td>registration</td>
		<td>UUID</td>
		<td>The registration associated with this state.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.3.s3.table1.row4">
		<td>stateId</td>
		<td>String</td>
		<td>The id for this state, within the given context.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.3.s4"></a>Multiple Document GET

Example endpoint: http://example.com/xAPI/activities/state

获取此上下文的所有状态数据的状态ID（Activity + Agent \ [+注册，如果指定了\]）。如果指定了“since”参数，则此参数限于自指定时间戳（独占）以来已存储或更新的条目。

**Content:** None.

**Returns:** `200 OK`, Array of State id(s)  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.3.s4.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with these states.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s4.table1.row2">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with these states.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s4.table1.row3">
		<td>registration</td>
		<td>UUID</td>
		<td>The Registration associated with these states.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.3.s4.table1.row4">
		<td>since</td>
		<td>Timestamp</td>
		<td>Only ids of states stored since the specified Timestamp (exclusive) are returned.</td>
		<td>Optional</td>
	</tr>
</table>

###### <a name="2.3.s5"></a>Multiple Document DELETE

Example endpoint: http://example.com/xAPI/activities/state

Deletes all state data for this context (Activity + Agent \[+ registration if specified\]).  

删除此上下文的所有状态数据（Activity + Agent \[+ registration 如果注册了\]）。

**Content:** None.

**Returns**: `204 No Content`  
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.3.s5.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s5.table1.row2">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with this state.</td>
		<td>Required</td>
	</tr>
	<tr id="2.3.s5.table1.row3">
		<td>registration</td>
		<td>UUID</td>
		<td>The Registration associated with this state.</td>
		<td>Optional</td>
	</tr>
</table>

<a name="agentsres"></a>

### <a name="2.4">2.4</a> Agents Resource

代理资源提供了一种方法来检索具有关于从外部服务（例如目录服务）派生的代理的组合信息的特殊对象。该资源具有与其关联的[并发](#concurrency) 控件。

###### <a name="2.4.s1"></a>Combined Information GET

###### <a name="2.4.s2"></a>Details

Example endpoint: http://example.com/xAPI/agents

为特定的代理返回一个特殊的Person对象。 Person对象与Agent对象非常相似，但是每个属性都有一个数值，而不是每个属性都有一个值，并且包含多个标识属性是合法的。这与FOAF人的概念不同，人们在这里用来表示以LBC代理人数据为中心的人的观点，但代理人只是指一个角色（一个人在一个上下文中）。

“agent”参数是具有单个标识符且不含数组的普通代理对象。它不是一个人物，也不是一个群体。

**Content:** None.

**Returns:** `200 OK`, Person Object

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.4.s2.table1.row1">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent representation to use in fetching expanded Agent information.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.4.s3"></a>Requirements
* <a name="2.4.s3.b1"></a>An LRS capable of returning multiple identifying properties for a Person 
Object SHOULD require the connecting credentials have increased, explicitly 
given permissions. 
* <a name="2.4.s3.b2"></a>An LRS SHOULD reject insufficiently privileged requests with `403 Forbidden`.
* <a name="2.4.s3.b3"></a>If an LRS does not have any additional information about an Agent to return, 
the LRS MUST still return a Person Object when queried, but that Person Object will only 
include the information associated with the requested Agent. 

__Note:__ This means that if a request is made for an Agent which the LRS has no 
prior knowledge of, it will still return a Person object containing the information 
about the Agent it received in the request. 

**注意：**这意味着如果请求的是LRS先前不知道的代理，它将返回一个Person对象，其中包含有关请求中收到的代理的信息。

###### <a name="2.4.s4"></a>Person Properties

###### <a name="2.4.s5"></a>Details

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.4.s5.table1.row1">
		<td>objectType</td>
		<td>String</td>
		<td><code>Person</code></td>
		<td>Required</td>
	</tr>
	<tr id="2.4.s5.table1.row2">
		<td>name</td>
		<td>Array of strings.</td>
		<td>List of names of Agents retrieved.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row3">
		<td><a href="http://xmlns.com/foaf/spec/#term_mbox">mbox</a></td>
		<td>Array of IRIs in the form "mailto:email address".</td>
		<td>List of e-mail addresses of Agents retrieved.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row4">
		<td><a href="http://xmlns.com/foaf/spec/#term_mbox_sha1sum">mbox_sha1sum</a></td>
		<td>Array of strings.</td>
		<td>List of the SHA1 hashes of mailto IRIs (such as go in an mbox property).</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row5">
		<td>openid*</td>
		<td>Array of strings.</td>
		<td>List of openids that uniquely identify the Agents retrieved.</td>
		<td>Optional</td>
	</tr>
	<tr id="2.4.s5.table1.row6">
		<td>account*</td>
		<td>Array of account objects.</td>
		<td>List of accounts to match. Complete account Objects (homePage and name) 
		MUST be provided.</td>
		<td>Optional</td>
	</tr>
</table>

See also: [Agent](./xAPI-Data.md#agent).

###### <a name="2.4.s6"></a>Requirements

* <a name="2.4.s6.b1"></a>All array properties MUST be populated with members with the same definition as the 
similarly named property from Agent Objects.  

* <a name="2.4.s6.b2"></a>Additional properties not listed here SHOULD* NOT be added to this object and each 
property MUST occur only once. 

<a name="activitiesres"></a> 

### <a name="2.5">2.5</a> Activities Resource

The Activities Resource provides a method to retrieve a full description of an Activity from the LRS. 
This resource has [Concurrency](#concurrency) controls associated with it.

活动资源提供了一种方法来从LRS中检索活动的完整描述。该资源具有与其关联的[并发](#concurrency) 控件。

###### <a name="2.5.s1"></a>Full Activity Object GET

Example endpoint: http://example.com/xAPI/activities

加载指定的完整活动对象。

**Content:** None.

**Returns:** `200 OK`, Content 
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.5.s1.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The id associated with the Activities to load.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.5.s2"></a>Requirements

* <a name="2.5.s2.b1"></a>If an LRS does not have a canonical definition of the Activity to return, the LRS SHOULD* 
still return an Activity Object when queried.

<a name="agentprofres"></a>

### <a name="2.6">2.6</a> Agent Profile Resource

###### <a name="2.6.s1"></a>Description


代理配置文件资源非常类似于状态资源，允许保存与代理相关的任意密钥/文档对。

###### <a name="2.6.s2"></a>Details

请求的语义由“profileId”参数驱动。如果包含，则GET方法将对“profileId”标识的单个已定义文档起作用。否则，GET将返回可用的ID。

###### <a name="2.6.s3"></a>Single Agent or Profile Document (PUT | POST | GET | DELETE)

Example endpoint: http://example.com/xAPI/agents/profile

在指定的代理上下文中存储，更改，提取或删除指定的Profile文档。

**Content (PUT | POST):** The document to be stored or updated.  
**Content (GET | DELETE):** None.  

**Returns (PUT | POST | DELETE):** `204 No Content`  
**Returns (GET):** `200 OK`, the Profile document  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.6.s3.table1.row1">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with this Profile document.</td>
		<td>Required</td>
	</tr>
	<tr id="2.6.s3.table1.row2">
		<td>profileId</td>
		<td>String</td>
		<td>The profile id associated with this Profile document.</td>
		<td>Required</td>
	</tr>
</table>

**注意：**“代理”参数是一个代理对象，而不是一个组。学习记录希望根据已识别组存储数据的提供者可以使用代理对象内的已识别组的标识符。

###### <a name="2.6.s4"></a>Multiple Document GET

Example endpoint: http://example.com/xAPI/agents/profile

获取代理的所有 Profile 文件的 Profile ID。如果指定了“since”参数，则此参数限于自指定时间戳（独占）以来已存储或更新的条目。

**Content:** None.

**Returns:** `200 OK`, Array of Profile id(s)  

<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.6.s4.table1.row1">
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>The Agent associated with this Profile document.</td>
		<td>Required</td>
	</tr>
	<tr id="2.6.s4.table1.row2">
		<td>since</td>
		<td>Timestamp</td>
		<td>Only ids of Profiles stored since the specified Timestamp 
			(exclusive) are returned.</td>
		<td>Optional</td>
	</tr>
</table>

<a name="actprofres"></a> 

### <a name="2.7">2.7</a> Activity Profile Resource

###### <a name="2.7.s1"></a>Description

活动配置文件资源非常类似于状态资源，允许保存与活动相关的任意密钥/文档对。

###### <a name="2.7.s2"></a>Details

请求的语义由“profileId”参数驱动。如果包含，则GET方法将对“profileId”标识的单个已定义文档起作用。否则，GET将返回可用的ID。

###### <a name="2.7.s3"></a>Single Document (PUT | POST | GET | DELETE)

Example endpoint: http://example.com/xAPI/activities/profile

在指定的活动的上下文中存储，更改，提取或删除指定的配置文件文档。

**Content (PUT | POST):** The document to be stored or updated.  
**Content (GET | DELETE):** None.  

**Returns (PUT | POST | DELETE)** `204 No Content`  
**Returns (GET):** `200 OK`, the Profile document  
<table>
	<tr><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.7.s3.table1.row1">
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with this Profile document.</td>
		<td>Required</td>
	</tr>
	<tr id="2.7.s3.table1.row2">
		<td>profileId</td>
		<td>String</td>
		<td>The profile id associated with this Profile document.</td>
		<td>Required</td>
	</tr>
</table>

###### <a name="2.7.s4"></a>Multiple Document GET

Example endpoint: http://example.com/xAPI/activities/profile

获取活动的所有配置文件的配置文件ID。如果指定了“since”参数，则此参数限于自指定时间戳（独占）以来已存储或更新的条目。

**Content:** None.

**Returns:** `200 OK`, Array of Profile id(s)  

<table>
	<tr id="2.7.s4.table1.row1"><th>Parameter</th><th>Type</th><th>Description</th><th>Required</th><tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>The Activity id associated with these Profile documents.</td>
		<td>Required</td>
	</tr>
	<tr id="2.7.s4.table1.row2">
		<td>since</td>
		<td>Timestamp</td>
		<td>Only ids of Profile documents stored since the specified Timestamp (exclusive) 
		are returned.</td>
		<td>Optional</td>
	</tr>
</table>


<a name="aboutresource"></a> 

### <a name="2.8">2.8</a> About Resource

###### <a name="2.8.s1"></a>Description

返回包含此LRS信息的JSON对象，包括支持的xAPI版本。

###### <a name="2.8.s2"></a>Rationale

此资源主要用于允许支持多个xAPI版本的客户端决定在与LRS进行通信时使用哪个版本。包含扩展以允许其他用途出现。

###### <a name="2.8.s3"></a>Details

###### <a name="2.8.s4"></a>Information GET

Example endpoint: http://example.com/xAPI/about

**Content:** None.

**Returns:** `200 OK`, JSON object containing basic metadata about this LRS
<table border="1">
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr id="2.8.s4.table1.row1">
		<td>version</td>
		<td>Array of version strings</td>
		<td>xAPI versions this LRS supports</td>
		<td>Required</td>
	</tr>
	<tr id="2.8.s4.table1.row2">
		<td>extensions</td>
		<td><a href="./xAPI-Data.md#miscext">Object</a></td>
		<td>A map of other properties as needed</td>
		<td>Optional</td>
	</tr>

</table>

###### <a name="2.8.s5"></a>Requirements

* <a name="2.8.s5.b1"></a>An LRS MUST return the JSON document described above, with a "version" property that includes
the latest minor and patch version the LRS conforms to, for each major version.
    * <a name="2.8.s5.b1.b1"></a>For version 1.0.0 of this specification, this means that `1.0.0` MUST be included;
    `0.9` and `0.95` MAY be included. (For the purposes of this requirement, `0.9` and `0.95`
    are considered major versions.)
* <a name="2.8.s5.b2"></a>Additional properties MUST NOT be added to this object outside of extensions and each 
property MUST occur only once.  
* <a name="2.8.s5.b3"></a>An LRS SHOULD allow unauthenticated access to this resource.
* <a name="2.8.s5.b4"></a>An LRS MUST NOT reject requests based on their version header as would otherwise be 
required by [Versioning](#versioning).

<a name="validation"></a> 

## <a name="3.0">3.0</a> Data Validation

###### <a name="3.0.s1"></a>Description

The function of the LRS within the xAPI is to store and retrieve Statements. As long as it has sufficient information 
to perform these tasks, it is expected that it does them. Validation of Statements in the Experience API is focused 
solely on syntax, not semantics. Enforcing the rules that ensure valid meaning among Verb definitions, Activity types, 
and extensions is the responsibility of the Learning Record Provider sending the Statement. 
LRS 中执行 xAPI 标准的函数是用来存储和检索声明的 。只要它有足够的信息来执行这些任务，就可以预期它们完成这些任务。 Experience API中的语句验证仅关注语法，而不是语义。学习记录提供者发送声明的责任是执行确保动词定义，活动类型和扩展之间有效含义的规则。

###### <a name="3.0.s2"></a>Requirements

* <a name="3.0.s2.b1"></a>The LRS SHOULD enforce rules regarding structure. 
* <a name="3.0.s2.b2"></a>The LRS SHOULD NOT enforce rules regarding meaning.  

<a name="concurrency"></a>

### <a name="3.1">3.1</a> Concurrency

##### <a name="3.1.s1"></a>Description
并发控制确保客户端不会将基于旧数据的PUT，POST或DELETE文档转换为LRS。

##### <a name="3.1.s2"></a>Details
xAPI will use HTTP 1.1 entity tags ([ETags](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19))
to implement optimistic concurrency control in the portions of the API where PUT, POST or DELETE might
overwrite or remove existing data, being:

在 PUT，POST或 DELETE 可能会覆盖或删除现有数据的部分，xAPI 将使用 HTTP 1.1 实体标签（[ETags](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19)）来实现API部分中的开放并发性的控件，这些部分如下所示：

* <a name="3.1.s2.b1"></a>State Resource
* <a name="3.1.s2.b2"></a>Agent Profile Resource 
* <a name="3.1.s2.b3"></a>Activity Profile Resource

##### <a name="3.1.s3"></a>Client Requirements

状态资源将允许没有并发头的PUT，POST和DELETE请求，因为状态冲突不太可能。下面的要求仅适用于代理配置文件资源和活动配置文件资源。

* <a name="3.1.s3.b1"></a>A Client making a PUT request to either the Agent Profile Resource or Activity Profile 
Resource MUST include the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header or the 
[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26) header.

* <a name="3.1.s3.b2"></a>A Client making a POST request to either the Agent Profile Resource or Activity Profile 
Resource SHOULD* include the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header or the 
[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26) header.

* <a name="3.1.s3.b3"></a>A Client making a DELETE request to either the Agent Profile Resource or Activity Profile 
Resource SHOULD* include the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header.

* <a name="3.1.s3.b4"></a>Clients SHOULD* use the ETag value provided by the LRS rather than calculating it themselves. 

##### <a name="3.1.s4"></a>LRS Requirements

* <a name="3.1.s4.b1"></a>An LRS responding to a GET request MUST add an ETag HTTP header to the response.
* <a name="3.1.s4.b2"></a>An LRS responding to a GET request without using a transfer encoding or using the identity 
transfer encoding MUST calculate the value of the ETag header to be a hexadecimal string of the SHA-1 digest of the contents. 
This hexadecimal string SHOULD be rendered using numbers and lowercase characters only; uppercase characters SHOULD NOT be used. 
The requirement to calculate the ETag this way will be removed in a future version of the specification.
* <a name="3.1.s4.b3"></a>An LRS responding to a GET request using any non-identity transfer encoding MUST NOT calculate 
the included ETag as above, due to the interpretation of ETags by existing web infrastructure.
* <a name="3.1.s4.b4"></a>As defined in [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19), 
an LRS responding to a GET request MUST enclose the header in quotes.  
* <a name="3.1.s4.b5"></a>An LRS responding to a PUT request MUST handle the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header as described in RFC2616, HTTP 1.1 if 
it contains an ETag, in order to detect modifications made after the Client last fetched the document.
* <a name="3.1.s4.b6"></a>An LRS responding to a PUT request MUST handle the "[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26)" header as described in 
RFC2616, HTTP 1.1 if it contains "*", in order to to detect when there is a resource present that the Client is not aware of.
* <a name="3.1.s4.b7"></a>An LRS responding to a POST or DELETE request SHOULD* handle the "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" header as described in RFC2616, HTTP 1.1 
if it contains an ETag, in order to detect modifications made after the Client last fetched the document.
* <a name="3.1.s4.b8"></a>An LRS responding to a POST request SHOULD* handle the 
"[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26)" header as described in RFC2616, HTTP 1.1 if it 
contains "*", in order to to detect when there is a resource present that the Client is not aware of.

如果上述两个 PUT 请求情况中的头部先决条件失败，则 LRS：

* <a name="3.1.s4.b9"></a>MUST return HTTP status `412 Precondition Failed`.
* <a name="3.1.s4.b10"></a>MUST NOT make a modification to the resource. 

如果上述任何POST或DELETE请求情况下的头部前置条件失败，则LRS：

* <a name="3.1.s4.b11"></a>SHOULD* return HTTP status `412 Precondition Failed`.
* <a name="3.1.s4.b12"></a>SHOULD* NOT make a modification to the resource. 

如果接收到的PUT请求中没有任何已存在的资源的标题，则LRS：

* <a name="3.1.s4.b13"></a>MUST return HTTP status `409 Conflict`.
* <a name="3.1.s4.b14"></a>MUST return a response explaining that the Learning Record Provider SHOULD
	* <a name="3.1.s4.b14.b1"></a>check the current state of the resource.
	* <a name="3.1.s4.b14.b2"></a>set the "If-Match" header with the current ETag to resolve the conflict.
* <a name="3.1.s4.b15"></a>MUST NOT make a modification to the resource.

<a name="errorcodes"></a> 

### <a name="3.2">3.2</a> Error Codes

##### <a name="3.2.s1"></a>Description

本规范定义了需求，其中一些要求强制LRS接受或拒绝请求，返回响应并在特定条件下执行其他行为。在需要LRS拒绝请求的情况下，相应的错误代码被列为需求的一部分。

这些要求都不符合这样的想法，即LRS也可以配置为拒绝请求，并根据超出本规范范围的条件作出不同的响应或行为。

其中一个条件是许可。例如，LRS可能会将权限分配给一组特定的凭证，以便这些凭证只能发出与特定代理有关的语句。然后，它可以拒绝使用与该代理无关的证书的任何陈述。除了部分[4.2](#oauthscope)中推荐的OAuth授权范围值列表外，LRS可分配的权限超出了本规范的范围。

权限还可以影响LRS向GET请求返回的响应。例如，一组证书可能只有权限查看有关特定Actor的语句，在这种情况下，LRS将过滤任何返回的语句以排除与该Actor无关的任何语句。有关详细信息，请参见[GET语句](#stmtresget) 。

在本规范明确允许的情况下，使用的凭证也会影响LRS在处理请求时的行为，例如，LRS通常会覆盖Statement的“authority”属性，但有时可以接受提交的授权信任关系与用于提交语句的凭证相关联。有关详细信息，请参见[权限](./xAPI-Data.md#authority) 。

由LRS设置的权限可能会导致技术上符合LRS的一致性测试失败。这可能会在测试软件提出的请求被拒绝的情况下发生。为此，LRS需要可配置，或者用于测试的凭证需要授予足够的权限，以便权限限制不会影响一致性测试的结果。

另一个条件是发送的请求超出了LRS设置的大小限制。期待LRS总是接受任何规模的请求是不合理的。 LRS可以选择它认为合适的任何尺寸限制，但需要进行配置，以便在一致性测试期间不应用尺寸限制。当然，由于硬件限制等原因，一致性测试期间仍会存在一些尺寸限制，但预计这些限制足够高以免影响测试运行。

LRS 还可以拒绝请求或在怀疑存在恶意的情况下撤销证书，例如在短时间内发生意外的大量请求。预计这一限制将足够高，以便在一致性测试期间提出的请求速率不会触发任何速率限制。

##### <a name="3.2.s2"></a>Details
The list below offers some general guidance on HTTP error codes that could be returned from various methods in the API. 

* <a name="3.2.s2.b1"></a>`400 Bad Request` - Indicates
an error condition caused by an invalid or missing argument. The term 
"invalid arguments" includes malformed JSON or invalid Object structures.

* <a name="3.2.s2.b2"></a>`401 Unauthorized` - Indicates that authentication is required, or in the 
case authentication has been posted in the request, that the given credentials have been refused.

* <a name="3.2.s2.b3"></a>`403 Forbidden` - Indicates that the request is unauthorized for the given 
credentials. Note this is different than refusing the credentials given. In this case, the credentials 
have been validated, but the authenticated Client is not allowed to perform the given action.

* <a name="3.2.s2.b4"></a>`404 Not Found` - Indicates the requested resource was not found. May be 
returned by any method that returns a uniquely identified resource, for instance, any State, Agent Profile, 
or Activity Profile Resource request targeting a specific document, or the method to retrieve a single Statement.

* <a name="3.2.s2.b5"></a>`409 Conflict` - Indicates an error condition due to a conflict with the 
current state of a resource, in the case of State Resource, Agent Profile Resource or Activity Profile Resource
requests, or in the Statement Resource PUT or POST calls. See Section [3.1 Concurrency](#concurrency) for more details.

* <a name="3.2.s2.b6"></a>`412 Precondition Failed` - Indicates an error condition due to a failure of 
a precondition posted with the request, in the case of State or Agent Profile or Activity Profile 
API requests. See Section [6.3 Concurrency](#concurrency) for more details.

* <a name="3.2.s2.b7"></a>`413 Request Entity Too Large` - Indicates that the LRS has rejected the Statement or 
document because its size (or the size of an Attachment included in the request) is larger than 
the maximum allowed by the LRS. 

* <a name="3.2.s2.b8"></a>`429 Too Many Requests` - Indicates that the LRS has rejected the request because it 
has received too many requests from the Client or set of credentials in a given amount of time. 

* <a name="3.2.s2.b9"></a>`500 Internal Server Error` - Indicates a general error condition, typically an 
unexpected exception in processing on the server.

##### <a name="3.2.s3"></a>Requirements

* <a name="3.2.s3.b1"></a>An LRS MUST return the error code most appropriate to the error condition from the list above.

* <a name="3.2.s3.b2"></a>An LRS SHOULD return a message in the response explaining the cause of the error.

* <a name="3.2.s3.b3"></a>An LRS SHOULD use content negotiation as described in [RFC 7231](http://tools.ietf.org/html/rfc7231#section-5.3) to decide the format of the error.

* <a name="3.2.s3.b4"></a>An LRS SHOULD allow for plain text, HTML, and JSON responses for errors (using content negotiation).

* <a name="3.2.s3.b5"></a>A Learning Record Provider SHOULD send an "Accept" header with requests to enable content negotiation.

* <a name="3.2.s3.b6"></a>The LRS SHOULD* reject any request with `400 Bad Request` status where the content type header 
does not match the content included in the request or where the structure of the request does not match the structure 
outlined in this specification for a particular content type. For example, if the content of the request is formatted as JSON, 
the content type is expected to be `application/json`. If the content type is application/x-www-form-urlencoded it is expected 
that the request will include a method parameter as outlined in [Alternate Request Syntax](#alt-request-syntax).

* <a name="3.2.s3.b7"></a>The LRS MUST reject with `400 Bad Request` status any requests that use any parameters which the LRS 
does not recognize in their intended context in this specification. 
( __Note:__ LRSs MAY recognize and act on parameters not in this specification).

* <a name="3.2.s3.b8"></a>The LRS MUST reject with `400 Bad Request` status any requests that use any parameters 
matching parameters described in this specification in all but case.

* <a name="3.2.s3.b9"></a>The LRS MUST reject a batch of statements if any Statement within that batch is rejected.

* <a name="3.2.s3.b10"></a>The LRS MUST reject with `403 Forbidden` status any request rejected by the LRS where the 
credentials associated with the request do not have permission to make that request. 

* <a name="3.2.s3.b11"></a>The LRS MUST reject with `413 Request Entity Too Large` status any request rejected by the LRS 
where the size of the Attachment, Statement or document is larger than the maximum allowed by the LRS.

* <a name="3.2.s3.b12"></a>The LRS MAY choose any Attachment, Statement and document size limits and MAY vary this limit 
on any basis, e.g., per authority.

* <a name="3.2.s3.b13"></a>The LRS MUST reject with `429 Too Many Requests` status any request rejected by the LRS where 
the request is rejected due to too many requests being received by a particular Client or set of credentials in a given 
amount of time. 

* <a name="3.2.s3.b14"></a>The LRS MAY choose any rate limit and MAY vary this limit on any basis, e.g., per authority.

The following requirements exist for the purposes of conformance testing, to ensure that any limitations or permissions 
implemented by the LRS do not affect the running of conformance testing software. 

* <a name="3.2.s3.b15"></a>The LRS SHOULD* be configurable not to reject any requests from a particular set of credentials 
on the basis of permissions. This set of credentials SHOULD* be used for conformance testing but MAY be deleted/deactivated 
on live systems. 

* <a name="3.2.s3.b16"></a>The LRS MUST be configurable to accept Attachments, Statements or documents of any reasonable 
size (see above).

* <a name="3.2.s3.b17"></a>The LRS MUST be configurable to accept requests at any reasonable rate. 

<a name="versioning"></a> 

### <a name="3.3">3.3</a> Versioning

###### <a name="3.3.s1"></a>Rationale

规范的未来修订可能会引入更改，例如添加到语句中的属性。使用语义版本将允许客户和LRS在规格更改时保持互操作性。

###### <a name="3.3.s2"></a>Details

从版本1.0.0开始，xAPI将根据[语义版本1.0.0](http://semver.org/spec/v1.0.0.html)进行版本控制。来自客户端的每个请求和来自LRS的每个响应都包含一个名为“X-Experience-API-Version”的HTTP标头，并且版本为值。例如，版本1.0.3的 `X-Experience-API-Version` ;请参阅本规范当前版本的[修订历史记录](./xAPI-About.md#Appendix1A) 。

**注意：**对于1.0.0之后的规范补丁版本，“X-Experience-API-Version”头文件与[statement version属性](./xAPI-Data.md#version) 1.0.0版本适用于该规范的所有1.0.x版本。 “X-Experience-API-Version”标题使LRS和客户端能够确定所遵循规范的确切补丁版本。尽管1.0.x版本之间不会出现通信不兼容问题，但有时还会澄清以前的预期行为。

###### <a name="3.3.s3"></a>LRS Requirements

* <a name="3.3.s3.b1"></a>The LRS MUST include the "X-Experience-API-Version" header in every response.
* <a name="3.3.s3.b2"></a>The LRS MUST set this header to the latest patch version.
* <a name="3.3.s3.b3"></a>The LRS MUST accept requests with a version header of `1.0` as if the version header was `1.0.0`.
* <a name="3.3.s3.b4"></a>The LRS MUST reject requests with version header prior to version 1.0.0 unless such requests are 
routed to a fully conformant implementation of the prior version specified in the header.
* <a name="3.3.s3.b4.1"></a>The LRS MUST reject requests without a version header unless such requests are 
routed to a fully conformant 0.9 implementation.
* <a name="3.3.s3.b5"></a>The LRS MUST accept requests with a version header starting with `1.0.` if the request is otherwise valid. 
* <a name="3.3.s3.b6"></a>The LRS MUST reject requests with a version header of `1.1.0` or greater.
* <a name="3.3.s3.b7"></a>The LRS MUST make these rejects by responding with a `400 Bad Request` error including a short 
description of the problem.

###### <a name="3.3.s4"></a>Client Requirements

* <a name="3.3.s4.b1"></a>The Client MUST include the "X-Experience-API-Version" header in every request.
* <a name="3.3.s4.b2"></a>The Client MUST set this header to the latest patch version.
* <a name="3.3.s4.b3"></a>The Client SHOULD tolerate receiving responses with a version of `1.0.0` or greater.
* <a name="3.3.s4.b4"></a>The Client SHOULD tolerate receiving data structures with additional properties.
* <a name="3.3.s4.b5"></a>The Client SHOULD ignore any properties not defined in version 1.0.0 of the spec.

###### <a name="3.3.s5"></a>Conversion Requirements

* <a name="3.3.s5.b1"></a>Statements of newer versions MUST NOT be converted into a prior version format, e.g., in order 
to handle version differences.
* <a name="3.3.s5.b2"></a>Statements of prior versions MAY be converted into a newer version only by following the methods 
described in [Appendix A: Converting Statements to 1.0.0](#Appendix3A).

<a name="authentication"></a>

## <a name="4.0">4.0</a> Authentication

###### <a name="4.0.s1"></a>Rationale

In order to balance interoperability and the varying security requirements of different environments, several 
authentication options are defined.

###### <a name="4.0.s2"></a>Details

规范中定义了以下认证方法。任何给定的LRS将至少实现其中一种方法，并可能实现本规范中未定义的其他方法。

* <a name="4.0.s2.b1"></a>[OAuth 1.0 (RFC 5849)](http://tools.ietf.org/html/rfc5849), with signature methods of 
"HMAC-SHA1", "RSA-SHA1", and "PLAINTEXT"
* <a name="4.0.s2.b2"></a>[HTTP Basic Authentication](http://tools.ietf.org/html/rfc7235)
* <a name="4.0.s2.b3"></a>Common Access Cards

虽然通用访问卡在本规范中定义为身份验证方法，但未定义此身份验证方法的实现细节。 xAPI工作组鼓励实施通用访问卡的LRS开发者作为一种认证方法，在本规范的未来版本中协作定义此认证方法的细节。

在本规范中没有提供进一步的细节来描述HTTP基本认证，因为这种认证方法在[RFC 7235](http://tools.ietf.org/html/rfc7235)中有明确和完整的定义。

###### <a name="4.0.s3"></a>Requirements

* <a name="4.0.s3.b1"></a>The LRS MUST support authentication using at least one of the authentication methods defined 
in this specification.

* <a name="4.0.s3.b2"></a>The LRS MUST handle making, or delegating, decisions on the validity of Statements, and 
determining what operations might be performed based on the credentials used.

<a name="authdefs"></a>

### <a name="4.1">4.1</a> OAuth 1.0 Authentication Scenarios and Methods

下面的矩阵和要求描述了OAuth中使用的可能的身份验证方案，并建议在这些方案中使用身份验证工作流程。针对每个场景描述的过程并不是全面的，而是标准OAuth工作流程的变化。

本节中的要求仅适用于LRS支持OAuth 1.0的情况。

一个 **已注册的应用程序** 是一个已向 LRS 并被 LRS 当做一个 OAuth 用户授权。

**已知用户**是 LRS 上的用户帐户，或LRS信任的用于定义用户的系统上的用户帐户。

<table border="1">
<tr><th></th><th>Known user</th><th>User unknown</th></tr>
<tr id="4.1.table1.row1">
<td>Application is registered</td>
<td>Standard workflow for OAuth.</td>
<td>LRS trusts application to access xAPI without additional user credentials. OAuth token steps are not invoked</td>
</tr>
<tr id="4.1.table1.row2">
<td>Application is not registered</td>
<td>The application Agent is not identified as a registered Agent and the LRS cannot make assumptions on its identity.</td>
<td></br></td>
</tr>
<tr id="4.1.table1.row3">
<td>No application</td>
<td>HTTP Basic Authentication is used instead of OAuth, since no application is involved.</td>
<td></br></td>
</tr>
<tr id="4.1.table1.row4">
<td>No authentication</td>
<td align="center"colspan="2">MAY be supported by the LRS, possibly for testing purposes.</td>

</tr>

</table>

##### <a name="4.1.s2"></a>Requirements

* <a name="4.1.s2.b1"></a>The LRS MUST record the application's name and a unique consumer key (identifier).
* <a name="4.1.s2.b2"></a>The LRS MUST provide a mechanism to complete this registration, or delegate to another system 
that provides such a mechanism.
* <a name="4.1.s2.b3"></a>The LRS MUST be able to be configured for complete support of the xAPI:
	* <a name="4.1.s2.b3.b1"></a>With any of the methods below.
	* <a name="4.1.s2.b3.b2"></a>In any of the workflow scenarios below.
* <a name="4.1.s2.b4"></a>The LRS MAY (for security reasons): 
	* <a name="4.1.s2.b4.b1"></a>Support a subset of the methods below.
	* <a name="4.1.s2.b4.b2"></a>Limit the known users or registered applications.
* <a name="4.1.s2.b5"></a>The LRS SHOULD at a minimum supply OAuth with "HMAC-SHA1" and "RSA-SHA1" signatures.

###### <a name="4.1.s3"></a>Application registered + known user Process and Requirements
**Process:** The standard workflow for OAUth 1.0 is used. 

**Requirements:**
* <a name="4.1.s3.b1"></a>The LRS MUST support the resources in [OAuth Authorization Scope](#oauthscope) to complete 
the standard OAuth workflow (details not in this specification).
* <a name="4.1.s3.b2"></a>If this form of authentication is used to record Statements and no authority is specified, the LRS 
SHOULD record the authority as a Group consisting of an Agent representing the registered application, and an Agent 
representing the known user.

###### <a name="4.1.s4"></a>Application registered + user unknown Process and Requirements

**Process:** 
The LRS honors requests that are signed using OAuth with the registered application's credentials and with an empty token 
and token secret.

**Requirements:**
* <a name="4.1.s4.b1"></a>If this form of authentication is used to record Statements, the LRS SHOULD record the authority 
as the Agent representing the registered application.

###### <a name="4.1.s5"></a>Application Not Registered + Known User Process and Requirements

**Process:**

学习记录提供程序使用包含空字符串的使用者密钥来调用临时凭证请求端点，以指定“consumer_name”和其他常用参数。 “consumer_name”包含表示请求访问的应用程序的字符串。

学习记录提供者然后使用从LRS获得的临时证书将用户的浏览器发送到资源所有者授权。资源所有者授权会显示一个页面，显示“consumer_name”以及警告：无法验证请求授权的应用程序的身份。

否则，该过程将遵循标准的OAuth工作流程。

**Requirements:**
* <a name="4.1.s5.b1"></a>If this form of authentication is used to record Statements, the LRS MUST record an authority 
that includes both that application and the authenticating user, as a Group, since OAuth specifies an application.

###### <a name="4.1.s6"></a>No Application + Known User Process and Requirements
**Process:**
Use a username/password combination provided by the LRS for use by the known user.

**Requirements:**
* <a name="4.1.s6.b1"></a>If this form of authentication is used to record Statements, the LRS SHOULD 
record the authority as the Agent representing the known user.

###### <a name="4.1.s7"></a>No Authorization Process and Requirements

* <a name="4.1.s7.b1"></a>Requests MUST include headers for HTTP Basic Authentication based on a username and password 
containing zero or more space characters. 
* <a name="4.1.s7.b2"></a>Requests SHOULD* include headers for HTTP Basic Authentication based on a username and password 
each consisting of an empty string. In this case the HTTP Basic Authentication header will be `Basic ` followed by a base64 
encoded version of the string `:`.  This results in the string `Basic Og==`.

This is in order to distinguish an explicitly unauthenticated request from a request that needs to be given a 
HTTP Basic Authentication challenge.

<a name="oauthscope"></a> 

### <a name="4.2">4.2</a> OAuth 1.0 Authorization Scope

##### <a name="4.2.s1"></a>Description
这些是范围建议，旨在使LRS和使用xAPI进行通信的应用程序能够协商访问级别，从而实现应用程序所需的内容，同时最大限度地减少滥用的可能性。每个范围的限制是对与请求关联的用户帐户上的任何安全限制的补充。

尽管本节中描述的 LRS 要求支持 [OAuth 1.0](http://tools.ietf.org/html/rfc5849)，但是本节中的元素依赖 [OAuth 2.0](http://tools.ietf.org/html/rfc6749#section-3.3)。

本节中的要求仅适用于LRS支持OAuth 1.0的情况。

##### <a name="4.2.s2"></a>Details

下表列出了xAPI范围值：
<table>
	<tr><th>Scope</th><th>Permission</th></tr>
	<tr id="4.2.s2.table1.row1"><td>statements/write</td><td>write any Statement</td></tr>
	<tr id="4.2.s2.table1.row2">
		<td>statements/read/mine</td>
		<td>read Statements written by "me", that is with an authority 
			matching what the LRS would assign if writing a Statement with 
			the current token.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row3"><td>statements/read</td><td>read any Statement</td>
	<tr>
		<td>state</td>
		<td>read/write state data, limited to Activities and Actors 
			associated with the current token to the extent it is 
			possible to determine this relationship.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row4">
		<td>define</td>
		<td>(re)Define Activities and Actors. If storing a Statement 
			when this is not granted, ids will be saved and the LRS 
			MAY save the original Statement for audit purposes, but 
			SHOULD NOT update its canonical representation of any 
			Actors or Activities.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row5">
		<td>profile</td>
		<td>read/write Profile document data, limited to Activities and Actors 
			associated with the current token to the extent it is 
			possible to determine this relationship.
		</td>
	</tr>
	<tr id="4.2.s2.table1.row6"><td>all/read</td><td>unrestricted read access</td></tr>
	<tr id="4.2.s2.table1.row7"><td>all</td><td>unrestricted access</td></tr>
</table>

###### <a name="4.2.s3"></a>OAuth Resources
<table>
	<tr>
		<th>Name</th>
		<th>Endpoint</th>
		<th>Example</th>
	</tr>
	<tr id="4.2.s3.table1.row1">
		<td>Temporary Credential Request</td>
		<td>OAuth/initiate</td>
		<td>http://example.com/xAPI/OAuth/initiate</td>
	</tr>
	<tr id="4.2.s3.table1.row2">
		<td>Resource Owner Authorization</td>
		<td>OAuth/authorize</td>
		<td>http://example.com/xAPI/OAuth/authorize</td>
	</tr>
	<tr id="4.2.s3.table1.row3">
		<td>Token Request</td>
		<td>OAuth/token</td>
		<td>http://example.com/xAPI/OAuth/token </td>
	</tr>
</table>

##### <a name="4.2.s4"></a>Example
范围列表确定正在请求的权限集。例如，教师可能会向应用程序（客户端）授予“语句/读取”权限，但是LRS仍然会将该工具限制为指导者可以直接使用其凭据查询LRS的语句（例如与学生相关的语句）。

##### <a name="4.2.s5"></a>Requirements

* <a name="4.2.s5.b1"></a>The LRS MUST accept a scope parameter as defined in [OAuth 2.0](http://tools.ietf.org/html/rfc6749#section-3.3).
* <a name="4.2.s5.b2"></a>The LRS MUST assume a requested scope of "statements/write" and "statements/read/mine" if no 
scope is specified.
* <a name="4.2.s5.b3"></a>The LRS MUST support the scope of "all" as a minimum.
* <a name="4.2.s5.b4"></a>The LRS MAY support other scopes.
* <a name="4.2.s5.b5"></a>The Client SHOULD request only the minimal needed scopes, to increase the chances that the 
request will be granted.
* <a name="4.2.s5.b6"></a>The parameters "consumer_name" and "scope" are not part of OAuth 1.0, and therefore if used MUST be passed 
as query string or form parameters, not in the OAuth header.  

<a name="security"></a>

## <a name="5.0">5.0</a> Security 

超出身份验证的安全性（包括对OAuth授权范围的解释）超出了本文档的当前范围，并作为实现细节留给了单个LRS提供商。鼓励实施者遵循行业最佳实践，例如，来自白宫首席信息官办公室的[HTTPS专用标准](https://https.cio.gov)。

在实现本规范时可能会出现安全问题，为了安全起见，实施者可能会选择违反一致性要求。在这些情况下，鼓励实施者考虑其实施决策的安全性和互操作性影响。无论如何，LRS仍然需要可配置，以便它能够通过一致性测试。

虽然其他安全问题超出了本规范的范围，但xAPI社区仍然致力于确定最佳安全实践。这项工作已经开始于[xAPIsec](https://github.com/xapisec/xapisec)。非常鼓励参与。

<a name="append3"></a>
## <a name="5.0.s1"></a>Appendices

<a name="Appendix3A"></a>

### <a name="A">Appendix A</a>: Converting Statements to 1.0.0

###### <a name="A.s1"></a>Rationale
这是一个 1.0.0 规范，因此实现者不必考虑规范的先前版本。然而，之前的版本确实看到了明显的采用。此数据转换是为了保留使用早期版本跟踪的数据而指定的，并以一致的方式将其提供给新的实施人员。

###### <a name="A.s2"></a>Details

###### <a name="A.s3"></a>Conversion of Statements created based on version 0.9

转换在0.9中创建的Statement的1.0.0客户端或其他系统必须遵循以下步骤：

* <a name="A.s3.b1"></a>If the Statement has been voided or uses Verbs, Activity types, or properties not included in the
 0.9 specification, do not convert it.
* <a name="A.s3.b2"></a>Prefix "verb" with `http://adlnet.gov/expapi/verbs/`.
* <a name="A.s3.b3"></a>Prefix any Activity ids which are not full absolute IRIs with `tag:adlnet.gov,2013:expapi:0.9:activities:`
* <a name="A.s3.b4"></a>Prefix any extension keys which are not full absolute IRIs with `tag:adlnet.gov,2013:expapi:0.9:extensions:`
* <a name="A.s3.b5"></a>Prefix Activity types with `http://adlnet.gov/expapi/activities/`
* <a name="A.s3.b6"></a>for each Agent (Actor):
    * <a name="A.s3.b6.b1"></a>Search for Inverse Functional Identifiers in this order: "mbox, mbox_sha1sum, openid,
    account". Keep the first populated Inverse Functional Identifier found and discard the rest.
    * <a name="A.s3.b6.b2"></a>For the above Inverse Functional Identifier, take the first element in the array and
    use that as the value of that Inverse Functional Identifier property, discarding any
    remaining elements.
    * <a name="A.s3.b6.b3"></a>If the "name" property is present, set it equal to the first element in the "name"
    array, discard the remaining elements.
    * <a name="A.s3.b6.b4"></a>Remove all remaining properties.
* <a name="A.s3.b7"></a>Remove the "voided" property from the Statement, if present. Remember, if the value of the
  voided property is `true`, then the Statement MUST NOT be converted.
* <a name="A.s3.b8"></a>Add `version": "1.0.0`
* <a name="A.s3.b9"></a>If an authority was not previously set, set the authority to an Agent identified by an account 
with a homePage set to the home page corresponding to the system performing the conversion and an accountName of `unknown`.
* <a name="A.s3.b10"></a>If the "statement" property in Context was set, remove it from the Statement.
* <a name="A.s3.b11"></a>Preserve all other properties without modification, including the "stored" property. The "stored" 
property will still be updated if the Statement is sent to an LRS.

###### <a name="A.s4"></a>Conversion of Statements created based on version 0.95

转换在0.95中创建的Statement的1.0.0客户端或其他系统必须遵循以下步骤：

* <a name="A.s4.b1"></a>If the Statement is voided, do not convert it.
* <a name="A.s4.b2"></a>Remove the "voided" property from the Statement, if present. Remember, if the value of the "voided" 
property is `true`, then the Statement MUST NOT be converted.
* <a name="A.s4.b3"></a>Add `version": "1.0.0`
* <a name="A.s4.b4"></a>If an authority was not previously set, set the authority to an Agent identified by an account 
with a homePage set to the home page corresponding to the system performing the conversion and an accountName of `unknown`.
* <a name="A.s4.b5"></a>If the Statement property in Context was set to anything other than a StatementRef, 
remove it from the Statement.
* <a name="A.s4.b6"></a>Preserve all other properties without modification, including the "stored" property. The "stored" 
property will still be updated if the Statement is sent to an LRS.


###### <a name="A.s5"></a>Example


A 0.9 Statement:
```
{
    "id": "d1eec41f-1e93-4ed6-acbf-5c4bd0c24269",
    "actor": {
        "objectType": "Person",
        "name": [
            "Joe Schmoe",
            "Joseph Schmoseph"
        ],
        "mbox": [
            "mailto:joe@example.com"
        ],
        "openid": [
            "http://openid.com/joe-schmoe"
        ]
    },
    "verb": "completed",
    "inProgress": false,
    "object": {
        "objectType": "Activity",
        "id": "http://www.example.com/activities/001",
        "definition": {
            "name": {
                "en-US": "Example Activity"
            },
            "type": "course"
        }
    },
    "result": {
        "completion": true
    },
    "context": {
        "instructor": {
            "objectType": "Person",
            "lastName": [
                "Dad"
            ],
            "firstName": [
                "Joe's"
            ],
            "mbox": [
                "mailto:joesdad@example.com"
            ]
        },
        "contextActivities": {
            "parent": {
                "objectType": "Activity",
                "id": "non-absolute-activity-id",
                "definition": {
                    "name": {
                        "en-US": "Another Activity"
                    }
                }
            }
        }
    },
    "timestamp": "2012-06-01T19:09:13.245Z",
    "stored": "2012-06-29T15:41:39.165Z"
}
```

Converted to 1.0.0:
```
{
    "version": "1.0.0",
    "id": "d1eec41f-1e93-4ed6-acbf-5c4bd0c24269",
    "actor": {
        "objectType": "Agent",
        "name": "Joe Schmoe",
        "mbox": "mailto:joe@example.com"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/completed",
        "display": {
            "en-US": "completed"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.example.com/activities/001",
        "definition": {
            "name": {
                "en-US": "Example Activity"
            },
            "type": "http://adlnet.gov/expapi/activities/course"
        }
    },
    "result": {
        "completion": true
    },
    "context": {
        "instructor": {
            "objectType": "Agent",
            "mbox": "mailto:joesdad@example.com"
        },
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "tag:adlnet.gov,2013:expapi:0.9:activities:non-absolute-activity-id",
                    "definition": {
                        "name": {
                            "en-US": "Another Activity"
                        }
                    }
                }
            ]
        }
    },
    "timestamp": "2012-06-01T19:09:13.245Z",
    "stored": "2012-06-29T15:41:39.165Z",
    "authority": {
        "objectType": "Agent",
        "account": {
            "homePage": "http://www.example.com",
            "name": "unknown"
        }
    }
}
```


<a name="Appendix3B"></a>

### <a name="B">Appendix B</a>: Table of All Resources

### <a name="B.s1"></a>Required Resources
<table>
	<tr>
		<th>Base Resource Endpoint of the LRS Precedes Each Endpoint</th>
		<th>Function</th>
	</tr>
	<tr id="B.s1.table1.row1">
		<td>statements</td>
		<td>Statement Storage/Retrieval</td>
	</tr>
	<tr id="B.s1.table1.row2">
		<td>agents</td>
		<td>Agent Object Storage/Retrieval</td>
	</tr>
	<tr id="B.s1.table1.row3">
		<td>agents/profile</td>
		<td>Agent Profile Resource</td>
	</tr>
	<tr id="B.s1.table1.row4">
		<td>activities</td>
		<td>Activity Object Storage/Retrieval</td>
	</tr>
	<tr id="B.s1.table1.row5">
		<td>activities/profile</td>
		<td>Activity Profile Resource</td>
	</tr>
	<tr id="B.s1.table1.row6">
		<td>activities/state</td>
		<td>State Resource</td>
	</tr>
	<tr id="B.s1.table1.row7">
		<td>about</td>
		<td>LRS Information</td>
	</tr>
</table>

### <a name="B.s2"></a>OAuth Resources
<table>
	<tr>
		<th>Base Resource Endpoint of the LRS Precedes Each Endpoint</th>
		<th>Function</th>
	</tr>
	<tr id="B.s2.table1.row1">
		<td>OAuth/initiate</td>
		<td>Temporary Credential Request</td>
	</tr>
	<tr id="B.s2.table1.row2">
		<td>OAuth/authorize</td>
		<td>Resource Owner Authorization</td>
	</tr>
	<tr id="B.s2.table1.row3">
		<td>OAuth/token</td>
		<td>Token Request</td>
	</tr>
</table>

<a name="Appendix3C"></a>

### <a name="C">Appendix C</a>: Cross Domain Request Example

[Alternate Request Syntax](#alt-request-syntax) outlines alternative syntax for use when the normal syntax cannot be used due 
to browser or querystring length restrictions. This appendix provides an example of a PUT request to the Statements Resource 
following this format. 

[Alternate Request Syntax](#alt-request-syntax) 概述了由于浏览器或查询字符串长度限制而无法使用正常语法时使用的替代语法。本附录提供了按照这种格式向语句资源发出PUT请求的示例。

Request using normal syntax:

```
URL: http://example.com/xAPI/statements
Method: PUT

Query String Parameters:
    statementId=c70c2b85-c294-464f-baca-cebd4fb9b348

Request Headers:
    Accept:*/*
    Accept-Encoding:gzip, deflate, sdch
    Accept-Language:en-US,en;q=0.8
    Authorization: Basic VGVzdFVzZXI6cGFzc3dvcmQ=
    Content-Type: application/json
    X-Experience-API-Version: 1.0.3
    Content-Length: 351

Content:
{"id":"c70c2b85-c294-464f-baca-cebd4fb9b348","timestamp":"2014-12-29T12:09:37.468Z","actor":{"objectType":"Agent","mbox":"mailto:example@example.com","name":"Test User"},"verb":{"id":"http://adlnet.gov/expapi/verbs/experienced","display":{"en-US":"experienced"}},"object":{"id":"http://example.com/xAPI/activities/myactivity","objectType":"Activity"}}

```

Request using alternative syntax:

```
URL: http://example.com/xAPI/statements?method=PUT&statementId=c70c2b85-c294-464f-baca-cebd4fb9b348
Method: POST

Request Headers:
    Accept:*/*
    Accept-Encoding:gzip, deflate, sdch
    Accept-Language:en-US,en;q=0.8
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 745

Content (with added line breaks and not URL encoded for readability):
    statementId=c70c2b85-c294-464f-baca-cebd4fb9b348
    &Authorization=Basic VGVzdFVzZXI6cGFzc3dvcmQ=
    &X-Experience-API-Version=1.0.3
    &Content-Type=application/json
    &Content-Length=351
    &content={"id":"c70c2b85-c294-464f-baca-cebd4fb9b348","timestamp":"2014-12-29T12:09:37.468Z","actor":{"objectType":"Agent","mbox":"mailto:example@example.com","name":"Test User"},"verb":{"id":"http://adlnet.gov/expapi/verbs/experienced","display":{"en-US":"experienced"}},"object":{"id":"http://example.com/xAPI/activities/myactivity","objectType":"Activity"}}
```
