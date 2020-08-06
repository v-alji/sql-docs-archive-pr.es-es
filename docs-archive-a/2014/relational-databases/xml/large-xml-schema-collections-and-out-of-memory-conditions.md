---
title: Las condiciones de memoria insuficiente y las grandes colecciones de esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443207bbbdff5db7e54d61fcebabe70e34cc540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751946"
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a><span data-ttu-id="3c63b-102">Las condiciones de memoria insuficiente y las grandes colecciones de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="3c63b-102">Large XML Schema Collections and Out-of-Memory Conditions</span></span>
  <span data-ttu-id="3c63b-103">Se puede producir una condición de memoria insuficiente durante una llamada a la función XML_SCHEMA_NAMESPACE() integrada de una colección de esquemas XML de gran tamaño o cuando intenta quitar colecciones de esquemas XML de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="3c63b-103">During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur.</span></span> <span data-ttu-id="3c63b-104">A continuación, se exponen las soluciones que se pueden aplicar en estos casos:</span><span class="sxs-lookup"><span data-stu-id="3c63b-104">The following are solutions you can use to handle this:</span></span>  
  
-   <span data-ttu-id="3c63b-105">Cuando la carga del sistema no es muy importante, use el comando DROP_XML_SCHEMA_COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="3c63b-105">When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command.</span></span> <span data-ttu-id="3c63b-106">Si no funciona correctamente, ponga la base de datos en modo de usuario único mediante la instrucción ALTER DATABASE y vuelva a probar DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="3c63b-106">If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again.</span></span> <span data-ttu-id="3c63b-107">Si la colección de esquemas XML existe en **master**, **model**o **tempdb**, se deberá reiniciar el servidor para el modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="3c63b-107">If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.</span></span>  
  
-   <span data-ttu-id="3c63b-108">Cuando llame a XML_SCHEMA_NAMESPACE, puede intentar recuperar un solo espacio de nombres XML, intentar realizar la llamada cuando la carga del sistema es menos importante o realizarla en modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="3c63b-108">When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c63b-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c63b-109">See Also</span></span>  
 [<span data-ttu-id="3c63b-110">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="3c63b-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
