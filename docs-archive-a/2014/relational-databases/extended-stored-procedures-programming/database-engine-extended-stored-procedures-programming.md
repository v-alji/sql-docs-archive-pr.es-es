---
title: Programar procedimientos almacenados extendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- gateway applications [SQL Server]
- extended stored procedures [SQL Server], about extended stored procedures
- Open Data Services [SQL Server]
- ODS [SQL Server]
ms.assetid: 561305cd-c803-48af-9eec-2c19f4d311ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 30792cc2b431e35a8f7df5ff7bbb2c228892d5c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675391"
---
# <a name="programming-extended-stored-procedures"></a><span data-ttu-id="3c278-102">Programación de procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="3c278-102">Programming Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="3c278-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3c278-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="3c278-104">En el pasado, los Servicios abiertos de datos se usaban para escribir las aplicaciones de servidor, como las puertas de enlace a entornos de bases de datos que no son de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c278-104">In the past, Open Data Services was used to write server applications, such as gateways to non-SQL Server database environments.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="3c278-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no admite las partes obsoletas de la API Servicios abiertos de datos.</span><span class="sxs-lookup"><span data-stu-id="3c278-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support the obsolete portions of the Open Data Services API.</span></span> <span data-ttu-id="3c278-106">La única parte de la API Servicios abiertos de datos original que todavía se admite en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son las funciones de procedimiento almacenado extendido, de modo que se ha cambiado el nombre de la API por el de la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="3c278-106">The only part of the original Open Data Services API still supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are the extended stored procedure functions, so the API has been renamed to the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="3c278-107">Con la aparición de las más recientes y eficaces tecnologías, como las consultas distribuidas y la integración CLR, se ha reemplazado en gran medida la necesidad de aplicaciones basadas en la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="3c278-107">With the emergence of newer and more powerful technologies, such as distributed queries and CLR Integration, the need for Extended Stored Procedure API applications has largely been replaced.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c278-108">Si tiene aplicaciones de puerta de enlace existentes, no puede utilizar opends60.dll que se distribuye con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3c278-108">If you have existing gateway applications, you cannot use the opends60.dll that ships with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run the applications.</span></span> <span data-ttu-id="3c278-109">Ya no se admiten las aplicaciones de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3c278-109">Gateway applications are no longer supported.</span></span>  
  
## <a name="extended-stored-procedures-vs-clr-integration"></a><span data-ttu-id="3c278-110">Procedimientos almacenados extendidos frente a integración CLR</span><span class="sxs-lookup"><span data-stu-id="3c278-110">Extended Stored Procedures vs. CLR Integration</span></span>  
 <span data-ttu-id="3c278-111">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], los procedimientos almacenados extendidos (XP) proporcionaban el único mecanismo disponible para que los programadores de aplicaciones de base de datos escribieran la lógica del servidor, que era difícil de expresar o imposible de escribir en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c278-111">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], extended stored procedures (XPs) provided the only mechanism that was available for database application developers to write server-side logic that was either hard to express or impossible to write in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3c278-112">La integración CLR es una alternativa más consolidada para escribir tales procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3c278-112">CLR Integration provides a more robust alternative to writing such stored procedures.</span></span> <span data-ttu-id="3c278-113">Además, con la integración CLR, la lógica que se solía escribir en forma de procedimientos almacenados generalmente se expresa mejor como funciones con valores de tabla, que permiten que los resultados generados por la función se consulten en las instrucciones SELECT incrustándolos en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="3c278-113">Furthermore, with CLR Integration, logic that used to be written in the form of stored procedures is often better expressed as table-valued functions, which allow the results constructed by the function to be queried in SELECT statements by embedding them in the FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c278-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c278-114">See Also</span></span>  
 <span data-ttu-id="3c278-115">[Información general sobre la integración de Common Language Runtime &#40;CLR&#41;](../clr-integration/common-language-runtime-integration-overview.md) </span><span class="sxs-lookup"><span data-stu-id="3c278-115">[Common Language Runtime &#40;CLR&#41; Integration Overview](../clr-integration/common-language-runtime-integration-overview.md) </span></span>  
 [<span data-ttu-id="3c278-116">Funciones con valores de tabla en CLR</span><span class="sxs-lookup"><span data-stu-id="3c278-116">CLR Table-Valued Functions</span></span>](../clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
  
  
