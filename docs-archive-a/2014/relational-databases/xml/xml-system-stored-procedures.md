---
title: Procedimientos almacenados del sistema XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
author: rothja
ms.author: jroth
ms.openlocfilehash: 2008294fe5bc532dfb6883656420b4189e4da7b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674666"
---
# <a name="xml-system-stored-procedures"></a><span data-ttu-id="1a605-102">Procedimientos almacenados del sistema XML</span><span class="sxs-lookup"><span data-stu-id="1a605-102">XML System Stored Procedures</span></span>
  <span data-ttu-id="1a605-103">SQL Server proporciona los siguientes procedimientos almacenados que se utilizan junto con OPENXML:</span><span class="sxs-lookup"><span data-stu-id="1a605-103">SQL Server provides the following system stored procedures that are used together with OPENXML:</span></span>  
  
-   [<span data-ttu-id="1a605-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a605-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql)  
  
-   [<span data-ttu-id="1a605-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a605-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql)  
  
 <span data-ttu-id="1a605-106">Para escribir consultas con OPENXML, primero debe crear una representación interna del documento XML llamando a **sp_xml_preparedocument**.</span><span class="sxs-lookup"><span data-stu-id="1a605-106">To write queries by using OPENXML, you must first create an internal representation of the XML document by calling **sp_xml_preparedocument**.</span></span> <span data-ttu-id="1a605-107">El procedimiento almacenado devuelve un identificador a la representación interna del documento XML.</span><span class="sxs-lookup"><span data-stu-id="1a605-107">The stored procedure returns a handle to the internal representation of the XML document.</span></span> <span data-ttu-id="1a605-108">A continuación, este identificador se pasa a OPENXML.</span><span class="sxs-lookup"><span data-stu-id="1a605-108">This handle is then passed to OPENXML.</span></span> <span data-ttu-id="1a605-109">OPENXML ofrece vistas del conjunto de filas del documento basándose en XPaths.</span><span class="sxs-lookup"><span data-stu-id="1a605-109">OPENXML provides rowset views of the document based on XPaths.</span></span> <span data-ttu-id="1a605-110">Concretamente, se trata de un patrón de filas y uno o varios patrones de columnas.</span><span class="sxs-lookup"><span data-stu-id="1a605-110">Specifically, this is one row pattern and one or more column patterns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a605-111">El identificador de documentos devuelto por **sp_xml_preparedocument** es válido mientras dure la sesión.</span><span class="sxs-lookup"><span data-stu-id="1a605-111">The document handle that is returned by **sp_xml_preparedocument** is valid for the duration of the session.</span></span>  
  
 <span data-ttu-id="1a605-112">La representación interna de un documento XML se puede quitar de la memoria llamando al procedimiento almacenado del sistema **sp_xml_removedocument** .</span><span class="sxs-lookup"><span data-stu-id="1a605-112">The internal representation of an XML document can be removed from memory by calling the **sp_xml_removedocument** system stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a605-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a605-113">See Also</span></span>  
 <span data-ttu-id="1a605-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a605-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="1a605-115">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1a605-115">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
