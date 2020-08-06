---
title: Implementar soluciones de modelo mediante XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML scripts [Analysis Services]
- scripts [Analysis Services], deployment
- deploying [Analysis Services], XML scripts
- Analysis Services deployments, XML scripts
ms.assetid: a8cb1837-fcac-4730-bea4-a72cf94d9f7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b78490c5ab6ad3ba5e52bb82d4be254e3f5f102b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750302"
---
# <a name="deploy-model-solutions-using-xmla"></a><span data-ttu-id="5c3a0-102">Implementar soluciones de modelo mediante XMLA</span><span class="sxs-lookup"><span data-stu-id="5c3a0-102">Deploy Model Solutions Using XMLA</span></span>
  <span data-ttu-id="5c3a0-103">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], la opción **CREATE To** del comando **Incluir la base de datos como** crea un script XML de una base de datos [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] completa o uno de sus objetos constituyentes.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the **CREATE To** option of the **Script Database As** command creates an XML script of an entire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or one of its constituent objects.</span></span> <span data-ttu-id="5c3a0-104">Después, el script resultante se puede ejecutar en otro equipo para volver a crear el esquema (metadatos) de la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c3a0-104">The resulting script can then be run on another computer to recreate the schema (metadata) of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="5c3a0-105">El script genera la base de datos completa y no existe ningún mecanismo para actualizar de forma incremental los objetos ya implementados al usar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-105">The script generates the entire database, and there is no mechanism for incrementally updating already deployed objects when using the script.</span></span> <span data-ttu-id="5c3a0-106">Tras ejecutar el script e implementar la base de datos, debe procesarse la nueva base de datos creada para que los usuarios puedan examinarla.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-106">After running the script and deploying the database, the newly created database must be processed before users can browse it.</span></span>  
  
 <span data-ttu-id="5c3a0-107">Para obtener más información sobre el comando **Incluir la base de datos como** , consulte [Documentar y crear scripts en una base de datos de Analysis Services](document-and-script-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="5c3a0-107">For more information about the **Script Database As** command, see [Document and Script an Analysis Services Database](document-and-script-an-analysis-services-database.md).</span></span>  
  
## <a name="modifying-object-properties-in-the-xml-script"></a><span data-ttu-id="5c3a0-108">Modificar propiedades de objeto en el script XML</span><span class="sxs-lookup"><span data-stu-id="5c3a0-108">Modifying Object Properties in the XML Script</span></span>  
 <span data-ttu-id="5c3a0-109">Al usar el comando **Incluir la base de datos como** , no puede modificar propiedades específicas (como el nombre de base de datos, las cadenas de conexión de origen de datos y la configuración de seguridad) de los objetos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-109">When using the **Script Database As** command, you cannot modify specific properties (such as the database name, data source connection strings, and security settings) of the database objects.</span></span> <span data-ttu-id="5c3a0-110">Estas propiedades deben modificarse de forma manual en el script una vez generada este o en la base de datos implementada tras ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-110">These properties must either be manually modified in the script after the script has been generated or modified in the deployed database after running the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5c3a0-111">El script XML no incluirá la contraseña si ésta se ha especificado en la cadena de conexión para un origen de datos o por motivos de suplantación.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-111">The XML script will not contain the password if this is specified in either the connection string for a data source or for impersonation purposes.</span></span> <span data-ttu-id="5c3a0-112">Puesto que en este escenario la contraseña es obligatoria para el procesamiento, deberá agregarla manualmente al script XML antes de su ejecución o bien agregarla después de la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="5c3a0-112">Since the password is required for processing purposes in this scenario, you will either need to add this manually to the XML script before it executes or add it after the XML script executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3a0-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c3a0-113">See Also</span></span>  
 <span data-ttu-id="5c3a0-114">[Implementar soluciones de modelo mediante el Asistente para la implementación](deploy-model-solutions-using-the-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="5c3a0-114">[Deploy Model Solutions Using the Deployment Wizard](deploy-model-solutions-using-the-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="5c3a0-115">Sincronizar bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5c3a0-115">Synchronize Analysis Services Databases</span></span>](synchronize-analysis-services-databases.md)  
  
  
