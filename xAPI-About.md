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
    *2.0.	[How To Use This Document](./xAPI-About.md#readingguidelines)  
    *2.1.	[MUST / SHOULD / MAY](./xAPI-About.md#def-must-should-may)  
       *2.2.	[Guidelines for Interpreting Descriptive Text and Tables](./xAPI-About.md#interpret-text-table)  
       *3.0.[Serialization and JavaScript Object Notation](./xAPI-About.md#json)
       *4.0.[Definitions](./xAPI-About.md#definitions) 
       *5.0.[xAPI Components](./xAPI-About.md#xapi-components) 
       *6.0.[Extending xAPI](./xAPI-About.md#extending-xapi) 
       *7.0.[Profiles and Communities of Practice](./xAPI-About.md#COPs)  
       *[Appendices](./xAPI-About.md#append1)  
       *[Appendix A: Revision History](./xAPI-About.md#Appendix1A)  
       *[Appendix B: cmi5 Example](./xAPI-About.md#Appendix1B)  
       *Part Two:[Experience API Data](./xAPI-Data.md#parttwo)  
       *1.0.[Documents](./xAPI-Data.md#documents) 
       *2.0.[Statements](./xAPI-Data.md#statements)  
       *2.1.	[Purpose](./xAPI-Data.md#statement-purpose)  
        *2.2.	[Formatting Requirements](./xAPI-Data.md#dataconstraints) 
        *2.3.	[Statement Lifecycle](./xAPI-Data.md#lifecycle) 
        *	2.3.1.	[Statement Immutability](./xAPI-Data.md#statement-immutability-and-exceptions) 
           *2.3.2.	[Voiding](./xAPI-Data.md#voided) 
            *2.4.	[Statement Properties](./xAPI-Data.md#statement-properties)  
           *	2.4.1.	[ID](./xAPI-Data.md#stmtid)  
             *2.4.2.	[Actor](./xAPI-Data.md#actor)  
             *2.4.3.	[Verb](./xAPI-Data.md#verb)  
             *2.4.4.	[Object](./xAPI-Data.md#object)  
             *2.4.5.	[Result](./xAPI-Data.md#result)  
             *2.4.6.	[Context](./xAPI-Data.md#context)  
             *2.4.7.	[Timestamp](./xAPI-Data.md#timestamp)  
             *2.4.8.	[Stored](./xAPI-Data.md#stored)  
             *2.4.9.	[Authority](./xAPI-Data.md#authority)  
             *2.4.10.	[Version](./xAPI-Data.md#version)  
             *2.4.11.	[Attachments](./xAPI-Data.md#attachments)  
             *2.5.[Retrieval of Statements](./xAPI-Data.md#retrieval)   
             *2.6.[Signed Statements](./xAPI-Data.md#signature)  
             *3.0.[Metadata](./xAPI-Data.md#metadata)
             *3.1.[IRI Requirements](./xAPI-Data.md#iri-requirements)  
             *3.2.[Hosted Metadata](./xAPI-Data.md#miscmeta)  
             *4.0.[Special Data Types and Rules](./xAPI-Data.md#special-data)  
             *4.1.[Extensions](./xAPI-Data.md#miscext) 
             *4.2.[Language Maps](./xAPI-Data.md#lang-maps)
             *4.3.[IRIs](./xAPI-Data.md#iris)
             *4.4.[UUIDs](./xAPI-Data.md#uuids)
             *4.5.[ISO 8601 Timestamps](./xAPI-Data.md#timestamps)
             *4.6.[ISO 8601 Durations](./xAPI-Data.md#durations)
             *[Appendices](./xAPI-Data.md#append2)  
             *[Appendix A: Example Statements](./xAPI-Data.md#Appendix2A)  
             *[Appendix B: Example statement objects of different types](./xAPI-Data.md#Appendix2B)  
             *[Appendix C: Example definitions for Activities of type "cmi.interaction"](./xAPI-Data.md#Appendix2C)  
             *[Appendix D: Example Signed Statement](./xAPI-Data.md#Appendix2D)  
             *Part Three:[Data Processing, Validation, and Security](./xAPI-Communication.md#partthree)  
             *1.0.[Requests](./xAPI-Communication.md#requests)
             *1.1.[HEAD Request Implementation](./xAPI-Communication.md#httphead)  
              *1.2.[Headers](./xAPI-Communication.md#headers) 
              *1.3.[Alternate Request Syntax](./xAPI-Communication.md#alt-request-syntax) 
              *1.4.[Encoding](./xAPI-Communication.md#encoding) 
              *1.5.[Content Types](./xAPI-Communication.md#content-types) 
             *1.5.1.	[Application/JSON](./xAPI-Communication.md#applicationjson) 
             *1.5.2.	[Multipart/Mixed](./xAPI-Communication.md#multipartmixed)
             *2.0.[Resources](./xAPI-Communication.md#datatransfer)   
              *2.1.[Statement Resource](./xAPI-Communication.md#stmtres) 
              *2.2.[Documents Resources](./xAPI-Communication.md#doctransfer) 
              *2.3.[State Resource](./xAPI-Communication.md#stateres) 
              *2.4.[Agents Resource](./xAPI-Communication.md#agentsres) 
              *2.5.[Activities Resource](./xAPI-Communication.md#activitiesres) 
              *2.6.[Agent Profile Resource](./xAPI-Communication.md#agentprofres) 
              *2.7.[Activity Profile Resource](./xAPI-Communication.md#actprofres) 
              *2.8.[About Resource](./xAPI-Communication.md#aboutresource) 
              *3.0.[Data Validation](./xAPI-Communication.md#validation)     
             *3.1.[Concurrency](./xAPI-Communication.md#concurrency)  
             *3.2.[Error Codes](./xAPI-Communication.md#errorcodes)
             *3.3     [Versioning](./xAPI-Communication.md#versioning)  
             *4.0.[Authentication](./xAPI-Communication.md#authentication)  
             *4.1.[OAuth 1.0 Authentication Scenarios and Methods](./xAPI-Communication.md#authdefs) 
             *4.2.[OAuth 1.0 Authorization Scope](./xAPI-Communication.md#oauthscope)
             *5.0[Security](./xAPI-Communication.md#security)
             *[Appendices](./xAPI-Communication.md#append3)  
             *[Appendix A: Converting Statements to 1.0.0](./xAPI-Communication.md#Appendix3A)  
             *[Appendix B: Table of All Resources](./xAPI-Communication.md#Appendix3B)  
             *[Appendix C: Cross Domain Request Example](./xAPI-Communication.md#Appendix3C)  

<a name="partone"></a>
# Part One: About the Experience API
# 第一部分：关于 Experience API

<a name="introduction-partone"></a>
## 1.0 Introduction
## 1.0 介绍
5 
Experience API（xAPI）是一个旨在记录和交换学习经验的的技术标准，它规定了描述学习体验的数据结构，并定义了如何以数字化方式交换这些数据。

xAPI 是由 Advanced Distributed Learning (ADL) 发起的。ADL 成立于 1997 年，旨在使美国的培训和教育体系中的管理和信息通讯标准化、现代化。从那时起，人们就意识到追踪记录正式的结构化的计算机支持下的培训之外的个人的学习经历的需求越来越重要。
在评估候选人是否适合该岗位或他们处理各种任务的能力时，需要考虑大范围的不管线上还是线下，正式或非正式的学习经验。这些信息往往是分散的，并且来自很多源。

出于这种需要，xAPI 社区和规范诞生了。xAPI 假定：
  * 需要能够分析处理学习经历的相关信息并且这些信息是由很多不同的源、平台和技术技术中分散输出的。
  * 开发一个通用的框架来收集、存储和交换这些信息是实现这一目标的最佳方式。

xAPI 的目标是：
* 更易于理解和比较各种环境、平台和技术记录的学习经历和最终产出的记录。
* 最大限度地提高服务的互操作性，这些服务用于创建，收集，存储和处理有关学习经验。
* 给试图构建并实现合规应用程序的用户提供指导。
* 提供合规测试。

下面的文件列出了旨在实现这些目标的 xAPI 规范。

<a name="readingguidelines"></a>
## 2.0 怎样使用此文档

这是一个描述 Experience API 如何实施的权威性文档。它是专门为意图应用此技术的个人或组织制定的技术文档，其目的是为了开发互操作工具，系统和服务，这些系统和服务互相独立并能够协同工作。

因为基于这个规范集的各种工具、系统和服务都详细罗列在下文中，本文档会尽可能使用非技术人员**能够理解的**语言和格式。出于这个原因，提供 Experience API 某一方面**高级概览**的部分会标记上**说明**或**原理**。而这个文档中的标记了比如**要求**，**细节**或者**样例**的项目则是更具技术性的。

本规范分为三个部分。第一部分就是本介绍。旨在提供一些背景知识和总览，以及如何阅读规范其余部分的指导性意见。

本规范的第二部分为本规范中使用的各种数据对象定义了数据模型。xAPI 数据模型中最重要的对象是 "Statement" 对象。本规范定义了 Statement 对象的属性（包括 "Actor"，"Verb"，"Object"， "Result" 和 "Context"）以及对这些属性赋值及表述的语法规范。这一部分有助于确保遵守这一规范的服务保持一致的数据结构。

本规范的第三部分阐述了在遵守规范的服务之间传递有关学习经验数据时必须使用的传输方法。这包括请求的格式和预期的响应。请注意，xAPI 中的通信不限于“学习记录库”（LRS）从“内容”中接收数据。LRS 可以与不同的服务通信，从“学习记录提供者”到“学习记录消费者”。xAPI 遵循 REST 软件体系结构样式的指导原则，因此这些数据通过 HTTP 请求和响应进行传输。第三部分还详述了用于在 LRS 和可信"用户"间交换信息的安全方法。

<a name="def-must-should-may"></a>
### 2.1 MUST / SHOULD / MAY 
### 2.1 必须 / 应当 / 可以
xAPI 规范为了保持系统的一致性定义了三个职责术语，分别为必须（MUST），应当（SHOULD），可以（MAY）。一个不遵从“必须（或者必须不）”要求的服务或系统是不符合一致性规范的。而不符合“应当”要求的则不违反一致性要求，但是违背了规范的建议。
可以则是一种选项，由开发人员选择是否采用，并不会影响系统的一致性。在要求语言之外使用的这些术语则不是指定要求，并且在文档会避免使用。必须（MUST），应当（SHOULD），可以（MAY），必须不（MUST NOT）和应当不（SHOULD NOT）的完整定义可以在 [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt) 中查看。

在“应当”之后使用星号（\*）表示强烈建议。在未来的版本中会将这些建议变为“必须”要求。不遵从这些建议可能会导致互用性风险，和/或要求则会因为建议的具体情况导致其他不同的问题。这些建议在这个版本中不能做为“必须”要求，因此它们将会成为突破性的改变。xAPI 项目组强烈建议采用此规范人员按照“必须”要求执行这些要求，但同时也会继续支持不实行此措施的用户。

<a name="interpret-text-table"></a>
### 2.2 Guidelines for Interpreting Descriptive Text and Tables
以之前的经验来看。如果参考文档技术性较强或是规范文档，直接解释它。而且对于冗长、繁多并详尽的解释和表格来说，这样最好，如果详尽的分析成各种要求列表反而更不直观和/或冗长。

本规范中使用表格定义属性，参数等列表的要求。表格定义了哪些属性是必须的，推荐的和可选的。通常，“可选的”概念与创建对象的服务有关，而接收和解释对象的服务需要能够解释该对象的所有属性。通常，因为数据在各种情况下可能都不相关，所以属性是可选的。如果数据在特定情况下是相关的，那么这个属性就是必须的。

如果可选属性或参数包含具有推荐或必须属性的对象，则只有在使用包含它们的属性或参数时才推荐或必须需要这些属性。

文档中也提供了样例并在附录中详细说明了如何实现。这些样例的内容是为了说明规范的要求而虚构的，而且样例中用于记录特定学习体验的方法也不一定是最佳的。样例用于解释规范要求，但并不是优先于规范要求

如果规范中不涉及与实现过程中某一特定方面，则这些细节超出了本规范的描述范围。实施者自己来决定采用什么合理方法。本规范也会避免含糊不清，即使在特定范围内没有要求，通常也会给出合理解释。

<a name="json"></a>
## 3.0 序列化和 JSON

序列化是将数据对象和结构转换为存储或传输格式的过程。这样就可以从结果中反序列化出原有数据对象。在某些情况下，序列化一个数据的方法不止一种。例如，一个值为 true 的布尔类型会因为使用不同的序列化而被表示为 `true` 或 `1`。

xAPI 的序列化遵循 JSON 规范（所以布尔值用 `true` 或 `false` 表示）。也可以使用其他序列化工具表示本文档中定义的对象，比如 XML。这些内容超出了本规范的描述范围，并且使用 JSON 之外的任何规范表示本规范中定义的对象不符合规范。

即使在 JSON 的规则中，数据如何被序列化也可能略有不同，尤其是时间日期相关的数据，因为这是 xAPI 的一种特定的数字，系统的许多功能都依赖于此来判别两个声明（Statement）是否相同。有关受此影响的声明（Statement）属性的更多详细信息，请参考[不变性与例外](./xAPI-Data.md#statement-immutability-and-exceptions)。

JSON 允许具有包含空对象的属性。这在 xAPI 中不推荐使用；如果声明不打算包含关于属性的数据，则预期该属性不会被使用。所有必需的属性都需要不为空。


<a name="definitions"></a>
## 4.0 术语定义

* [Activity](#def-activity)
* [Activity Provider (AP)](#def-activity-provider)
* [Actor](#def-actor)
* [Application Programming Interface (API)](#def-api)
* [Authentication](#def-authentication)
* [Authorization](#def-authorization)
* [Community of Practice](#def-community-of-practice)
* [Document Profile Resource](#def-document-profile)
* [Endpoint](#def-endpoint)
* [Experience API (xAPI)](#def-experience-api)
* [Immutable](#def-immutable)
* [Internationalized Resource Identifier (IRI)](#def-iri)
* [Internationalized Resource Locator (IRL)](#def-irl)
* [Inverse Functional Identifier](#def-inverse-functional-identifier)
* [Learning Experience](#def-learning-experience)
* [Learning Management System (LMS)](#def-learning-management-system)
* [Learning Record](#def-learning-record)
* [Learning Record Consumer (LRC)](#def-learning-record-consumer)
* [Learning Record Provider (LRP)](#def-learning-record-provider)
* [Learning Record Store (LRS)](#def-learning-record-store)
* [Metadata Consumer](#def-metadata-consumer)
* [Metadata Provider](#def-metadata-provider)
* [Persona](#def-persona)
* [Profile](#def-profile)
* [Registration](#def-registration)
* [Representational State Transfer (REST)](#def-rest)
* [Service](#def-service)
* [Statement](#def-statement)
* [Tin Can API (TCAPI)](#def-tcapi)
* [Verb](#def-verb)
* [Vocabulary](#def-vocabulary)

<a name="def-activity"></a>

__Activity__ ：用于装配给“我做了什么”中的“什么”的对象类型；这是与 Actor 交互的某件事物。它可以是一种指令，经验或者表现，可以被追踪并与 Verb 有意义的组合，Activity 的解释是很宽泛的，这意味着 Activity 甚至可以是诸如椅子（真实或虚拟的）这样的有形物体。在 “Anna tried a cake recipe（安娜尝试了一种蛋糕配方）” 这个声明中， recipe（配方）构成了 xAPI 声明中的 Activity。Activities 的其他例子可以是一本书，一门在线学习课程，一次徒步旅行或者一次会议。

<a name="def-activity-provider"></a>

__Activity Provider (AP)__ ： 现在被称为学习记录提供者（Learning Record Provider）。这种改变辨析出了 activity 并不总是软件，而应该只是被追踪的事物。

<a name="def-actor"></a>

__Actor__ ：在声明中执行一个动作产生活动的一个被追踪的个体或团体。是“我做了什么”中的“我”。

<a name="def-api"></a>

__Application Programming Interface (API)__ ：一套用于访问软件应用或工具的规则和标准、

<a name="def-authentication"></a>

__Authentication__ ：表示身份验证。身份验证可让两个“可信”方进行交互。

<a name="def-authorization"></a>

__Authorization__ ：基于角色的权限管理；让一方“信任”另一方的过程。

<a name="def-client"></a>

__Client__ ：指可能通过请求进行交互的任何实体。举例来说，可以是学习记录提供者，学习记录消费者，学习记录库（LRS）或者学习管理系统（LMS）。

<a name="def-community-of-practice"></a>

__Community of Practice (CoP)__ :由一个共同的原因，角色或目的而联系起来的一群从业人员，它以一套通用的程序运作。Cop 专注于在特定知识领域或用例中实施 xAPI。Cop 或独立开发者可以创建特定领域的词汇表，配置文件和配方。这些实践通常涉及定义围绕案例和策划的各种词汇术语、同义词以及可能在CoP中首选的其他相关元数据的工作。他们还可以重用已由其他 CoP 或 xAPI 社区参与者发布的现有词汇表、配置文件和配方。

<a name="def-document-profile"></a>

__Document Profile Resource__: 一种保存了学习者或活动的信息的结构，通常是对教学系统组件有意义的名称/文档（name/document）对中。不要与 [Profile](#def-profile) 混淆。

<a name="def-endpoint"></a>

__Endpoint__: An entry point in a service-oriented-architecture.  xAPI mirrors this approach with resources 
by defining the IRI from which communication takes place as an endpoint.

__Endpoint__ ： 面向服务架构中的入口点。xAPI 使用这种方法映射资源

<a name="def-experience-api"></a>

__Experience API (xAPI)__ ： 本文档中阐述的规则集合，它决定了如何定义、格式化和交换学习经验，以使独立软件程序可以交换和使用这些信息。

<a name ="def-immutable"></a>

__Immutable__ ： 用于描述无法改变的事物的形容词。除了一些例外情况，xAPI 中的声明是不可变的。这去确保了在 LRS 之间共享声明时，声明的多个副本保持一致。
<a name="def-iri"></a>
 
__Internationalized Resource Identifier  (IRI)__ ： 一种唯一的标识符，可能是一个 IRL。用于确定一个对象，诸如一个 verb，activity 或 activity 类型。与 URI 不同，IRI 可以包含 ASCII 字符集以外的一些字符以支持各种不同语言。

IRI 总是包含一个图式。这不是本标准的要求，而是根据 [RFC 3987](http://www.ietf.org/rfc/rfc3987.txt) 定义的 IRI 的一部分。有时被称作“relative IRIs”而不是 IRI。

<a name="def-irl"></a>

__Internationalized Resource Locator (IRL)__ ：在本文件中，IRL 是 IRI 按照转换规范转换成 URI后的结果，它是一个 URL。

<a name="def-inverse-functional-identifier"></a>

__Inverse Functional Identifier__ ：对特定角色或小组唯一的标示符。
<a name="def-learning-experience"></a>

__Learning Experience__ ：与学习相关的事件。尽可能的多样化。例如，阅读一本书，参加在线课程，参加实地考察，从事自主式研究或获得完成课程的证书。

<a name="def-learning-management-system"></a>

__Learning Management System (LMS)__ ：“用于管理一个或多个学习者使用一门或多门课程的软件包。通常，LMS会一个基于网络的系统，它允许学习者进行自主认证，注册课程，完成课程并获得评估”（Learning Systems Architecture Lab 定义）。本文档中的 LMS 用作用户如何在系统中被识别为“可信”并能够访问其学习体验的示例。

<a name="def-learning-record"></a>

__Learning Record__ : 根据 xAPI 规范格式化的学习经验记录。学习记录（Learning Record）采用多种形式，包括声明，文件及其部分。该定义旨在包含所有内容。

<a name="def-learning-record-consumer"></a>

__Learning Record Consumer (LRC)__ ：一个用于访问学习记录库存储的数据并处理数据的 xAPI 客户端，通常用于解释，分析，转换，分发和聚合。

<a name="def-learning-record-provider"></a>

__Learning Record Provider (LRP)__ ： 将数据发送到学习记录库的 xAPI 客户端。通常，学习记录提供者创建学习记录，同时作为学习经验的一部分监控学习者。

<a name="def-learning-record-store"></a>

__Learning Record Store (LRS)__ ： 负责对学习记录接收、存储和提供的服务器（即能接收和处理网络请求的服务器）。

<a name="def-metadata-consumer"></a>

__Metadata Consumer__ ：一个人、组织、软件程序或者其他事物，旨在确定本规范中使用的 IRI 表示含义和/或检索有关 IRI 的元数据。LRS 可能是或不是 metadata consumer。

<a name="def-metadata-provider"></a>

__Metadata Provider__ ：一个人、组织、软件程序或者其他事物，它们将本规范中根据规范创建会被使用的 IRI 和/或托管有关 IRI 的元数据。

<a name="def-persona"></a>

__Persona__ ：一组一个或多个用于定义唯一用户的标示。概念上讲，这就像有一个“家庭电子邮件地址”和“工作电子邮件地址”。两者都是同一个人，但是有不同的数据，关联等。

<a name="def-profile"></a>

__Profile__ ： 在特定情况下实施 xAPI 的一组特定规则和文档。配置文件通常会提供特定的术语词汇表，其中一些是专门我配置文件创建的，另一些则从其他词汇表中引用。有时候有人会在不创建配置文件的情况下从多个来源获取词汇表。不要与 [Document Profile Resource](#def-document-profile) 混淆。

<a name="def-registration"></a>

__Registration__: 体验特定 Activity 的 Actor 实例。

<a name="def-rest"></a>

__Representational State Transfer (REST)__ ：用于设计联网 Web 服务的架构。它依赖于 HTTP 方法并使用当前 Web 最佳实践。

<a name="def-service"></a>

__Service__ ：负责分布式学习过程的一个或多个方面的软件组件。LMS 通常结合许多服务来设计完整的学习体验。

<a name="def-statement"></a>

__Statement__ ：用于展现经验和事件的数据结构，它们在 xAPI 中被追踪并当做学习记录的，可以是任何类型的。适时的表示一个事件的几个声明组成一组可以用于追踪记录一个学习经验的完整细节。

<a name="def-tcapi"></a>

__Tin Can API (TCAPI)__ ：本文档中定义的 API 的曾用名，通常用于  Experience API 的非正式引用。
<a name="def-verb"></a>

__Verb__: Is the action being done by the Actor within the Activity within a Statement. 
A Verb represents the "did" in "I did this".
__Verb__: 是由 Actor 在 Activity 中做出带有 Statement 的动作。表示”我做了什么“中的”做了“。

<a name="def-vocabulary"></a>

__Vocabulary__ ：CoP 用于标记或分类特定领域信息的术语表或汇总。词汇表的使用确保了每个人都使用了同一个词来表示同一个事物。有关词汇表的更多信息，请参见 [xAPI Vocabulary Companion Specification](https://github.com/adlnet/companion-specification-for-xapi-vocabularies/blob/master/SUMMARY.md)。

<a name="xapi-components"></a>

## 5.0 xAPI 组件

这一部分将以图形方式解释和展现不同的 xAPI 如何组合在一起。

##### 经验追踪

###### Figure 1: Data Flow in xAPI
![Data Flow in xAPI](./xAPIDataFlow.jpg)

Figure 1 shows the tracking of learning experiences. A learner has a learning experience. This experience could take place in an 
online course, it could be on the job or it could be part of recreation. It really could be anything. This experience is tracked, 
on the learner’s behalf, by a trusted Learning Record Provider (LRP). The Learning Record Provider can also be responsible for the 
trusted relationship between the experience and the learner. This might even include launching content for the learner and 
managing digital rights associated with the content.  

The Learning Record Provider creates Learning Records and sends them to one or more Learning Record Stores (LRSs). The LRS stores
the Learning Records and makes them available to any authorized Client. A Learning Record Consumer (LRC) is a type of Client that accesses 
Learning Records and makes use of them.

##### Activity Data and Metadata

###### Figure 2: xAPI Activity Data and Metadata
![xAPI Activity Data and Metadata](./xAPIMetadata.jpg)

Understanding how a single Activity (as uniquely identified by its IRI) is defined and described is a key concept in xAPI. 
Figure 2 shows this process. An Activity (as a part of a Statement) has metadata properties that may be populated within the 
Statement itself. This is done in the Statement's Activity Definition. The id of each Activity is an IRI which also could have 
metadata located at the resolution location of the IRI. Any metadata where the IRI resolves is under the control of the Metadata 
Provider. The Metadata Provider is also responsible for making sure the IRI is permanent and resolves correctly.

Any metadata located at where the IRI resolves is the authoritative source of metadata, and could be used to populate the LRS's 
canonical version of the Activity's metadata (LRS's Activity Definition) as a preference to what it receives from Statements. 
A Metadata Consumer can access metadata via the IRI for the authoritative version or can query the Activities Resource for the 
canonical version.

##### Agent and Persona Management

###### Figure 3: xAPI Agent and Persona Management
![xAPI Activity Data and Metadata](./xAPIPersonas.jpg)

xAPI grants the framework for allowing selective access to one's personal data. This is done through the management of what are 
called personas. In xAPI, each persona represents the "I" in "I did this" and is logically the subject of the Statement. Each 
Agent or Group in xAPI corresponds to a persona. A learner sending Learning Records to an LRS could have multiple personas (Agents) 
associated with him or her. 

In Figure 3, a learner accesses multiple services. Some of these services are used at work, others at home.  Some are used for 
social purposes and others are used for educational or professional puproses.  Thus, there are multiple personas functioning 
collectively within these services.  Each of these services send data to the LRS. Afterwards, there are Statements from three 
different personas of the same learner. 

The LRS can aggregate all of the information of each of the personas into one "Person" Object. This object can be retrieved from 
The LRS via the [Agents Resource](./xAPI-Communication.md#agentsres). How the LRS knows that these 
multiple personas belong to a single person is out of scope of this specification and there are several different approaches
that an LRS can take. It's also possible that some LRSs will have no mechanism for associating personas. 

<a name="extending-xapi"></a>

## 6.0 Extending xAPI

xAPI can be extended in a few ways. The most notable are Statement extensions, which allow great flexibility within Statements. 
It is recommended that Communities of Practice agree on how to use extensions for their particular use cases and utilize 
profiles whenever possible. Implementation details are covered in [4.1 Extensions](./xAPI-Data.md#miscext).

The About Resource is another instance where xAPI supports extensions.  The LRS may find it useful to communicate features or 
behaviors beyond this specification. The LRS can use extensions to the About Resource to facilitate this communication.

Finally, the set of resources implemented is not expected to be constrained by this document. Resources beyond 
those listed in this specification can be implemented and co-exist with the resources defined in this specification.

<a name="COPs"></a>

## 7.0 Profiles, Vocabularies, and Communities of Practice

xAPI strictly defines the structure of Statements, but is very flexible as to the contents of that structure. For example, the 
specification requires that all Statements have a "verb" property, but does not restrict the values of that property; any Verb 
can be used. This flexibility enables xAPI to be used in any context, including future use cases not envisaged by the 
specification authors.

It is intended that [Communities of Practice (CoPs)](#def-community-of-practice) will define Verbs, Activity types, 
contextual relationships, extensions, etc. 
to be used in their profiles by providing unique identifiers wherever applicable. The CoP will define these identifiers and 
their metadata in a [Vocabulary](#def-vocabulary). A profile is a set of rules and vocabularies to implemented in addition to 
xAPI for the particular use case being addressed. It is very important that such communities exist and share best practices. 
For more information on publishing vocabularies, see the [Vocabulary Companion Specification](https://adl.gitbooks.io/companion-specification-for-xapi-vocabularies/content) and [Vocabulary Primer](https://adl.gitbooks.io/experience-xapi-vocabulary-primer/content/) documents.

It is recommended that a profile use a unique "category" within a Statement's context to refer to any Statement  
which implements the profile.  An example profile is [cmi5](https://github.com/AICC/CMI-5_Spec_Current), 
which is designed for the traditional single learner, single online learning use case.  An example cmi5 Statement can 
be found in [Appendix B: cmi5 Example](#Appendix1B).

CoPs are highly recommended to avoid duplication of effort, as creating too many ways to solve the same problem 
will cause fragmentation in similar domains and can potentially hurt interoperability.  An example of a CoP for the medical 
field is the [MedBiquitous Learning Experience Working Group](http://groups.medbiq.org/medbiq/display/XIG/Learning+Experience+Group+Home).


<a name="append1"></a>
## Appendices

<a name="Appendix1A"></a>
### Appendix A: Revision History
###### 0.8 (Project Tin Can API Deliverable) to 0.9 (March 31, 2012)  

Rustici Software, who delivered the Project Tin Can API, made modifications to the 
API prior to the April 2012 Kickoff Meeting. It was voted in this meeting to 
move those changes into the current specification and revision to 0.9.

###### 0.90 to 0.95 (August 31, 2012)  

"Core" Verbs and Activity types were removed from the specification. References 
to these verbs in results, context, interactions, and Activity Definitions were 
also removed. It was recommended that implementers prefer community defined 
verbs to creating their own verbs.
- Verbs, Activity types, and extension keys are now URIs
- Restructured and added language around some of the other implementation details and scope.
- Changed from using a person-centric view of Agents to a persona-centric view.
- Friend of a Friend (FOAF) Agent merging requirement was removed.
- Agent Objects now have exactly 1 uniquely identifying property, instead of at least one.

###### 0.95 to 1.0.0 (April 26, 2013) 
Various refinements and clarifications including:
- Adding Attachments
- Activity metadata is now stored as JSON rather than XML
- Changes to voiding Statements
- Clarification and naming of the Document APIs (later renamed to Document Resources)
- Changes to querying the Statement API
- Signed Statements

[0.95...1.0.0](https://github.com/adlnet/xAPI-Spec/compare/0.95-spec...1.0.0)

###### 1.0.0 to 1.0.1 (October 1, 2013)
Clarifications and additional examples including:
- Fixed various typos
- Added additional examples in the appendices

[1.0.0...1.0.1](https://github.com/adlnet/xAPI-Spec/compare/1.0.0...1.0.1)

###### 1.0.1 to 1.0.2 (October 1, 2014)
- Added optional/required to tables
- Added missing table heading on Interaction components
- Change yes/no to required/optional in attachments
- Clarified intent of 'moreInfo' property

[1.0.1...1.0.2](https://github.com/adlnet/xAPI-Spec/compare/1.0.1...1.0.2)

###### 1.0.2 to 1.0.3 (September 21, 2016)
- Complete reorganization of the document into three parts
- Many, many clarifications
- Definitions slightly modified and greatly clarified
- Removed back-references to SCORM
- Additional explanatory text and diagrams
- Rename Statement API and Document APIs to Statement Resource and Document Resources

[1.0.2...1.0.3](https://github.com/adlnet/xAPI-Spec/compare/1.0.2...1.0.3)

<a name="Appendix1B"></a>
### Appendix B: cmi5 Example 

The following example illustrates a statement following the cmi5 Community of Practice. It demonstrates use of extensions 
and "category" contextActivities.

```
{  
  "id":"2a41c918-b88b-4220-20a5-a4c32391a240",
  "actor":{  
    "objectType":"Agent",
    "name":"Gert Frobe",
    "account":{  
      "homePage":"http://example.adlnet.gov",
      "name":"1625378"
    }
  },
  "verb":{  
    "id":"http://adlnet.gov/expapi/verbs/failed",
    "display":{  
      "en-US":"failed"
    }
  },
  "object":{  
    "id":"https://example.adlnet.gov/AUidentifier",
    "objectType":"Activity"
  },
  "result":{  
    "score":{  
      "scaled":0.65,
      "raw":65,
      "min":0,
      "max":100
    },
    "success":false,
    "duration":"PT30M",
    "extensions":{  
      "https://w3id.org/xapi/cmi5/result/extensions/progress":100
    }
  },
  "context":{  
    "registration":"ec231277-b27b-4c15-8291-d29225b2b8f7",
    "contextActivities":{  
      "category":[  
        {  
       	  "id":"https://w3id.org/xapi/cmi5/context/categories/moveon"
        },
        {  
          "id":"https://w3id.org/xapi/cmi5/context/categories/cmi5"
        }
      ]
    },
    "extensions":{  
      "https://w3id.org/xapi/cmi5/context/extensions/sessionid":"458240298378231"
    }
  },
  "timestamp":"2012-06-01T19:09:13.245+00:00"
}
```
