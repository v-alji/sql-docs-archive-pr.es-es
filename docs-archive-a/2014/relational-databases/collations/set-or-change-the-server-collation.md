---
title: Configurar o cambiar la intercalación del servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- server collations [SQL Server]
- collations [SQL Server], server
ms.assetid: 3242deef-6f5f-4051-a121-36b3b4da851d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7be051c8cf63a272f2bf42fb54b1c45ed4160
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677687"
---
# <a name="set-or-change-the-server-collation"></a><span data-ttu-id="bf3e8-102">Configurar o cambiar la intercalación del servidor</span><span class="sxs-lookup"><span data-stu-id="bf3e8-102">Set or Change the Server Collation</span></span>
  <span data-ttu-id="bf3e8-103">La intercalación de servidor actúa como intercalación predeterminada para todas las bases de datos del sistema que se han instalado con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], así como las bases de datos de usuario recién creadas.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-103">The server collation acts as the default collation for all system databases that are installed with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and also any newly created user databases.</span></span> <span data-ttu-id="bf3e8-104">La intercalación de servidor se especifica durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf3e8-104">The server collation is specified during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="bf3e8-105">Para más información, consulte [Compatibilidad con la intercalación y Unicode](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="bf3e8-105">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
## <a name="changing-the-server-collation"></a><span data-ttu-id="bf3e8-106">Cambiar la intercalación de servidor</span><span class="sxs-lookup"><span data-stu-id="bf3e8-106">Changing the Server Collation</span></span>  
 <span data-ttu-id="bf3e8-107">El cambio de la intercalación predeterminada para una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede ser una operación compleja que incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="bf3e8-107">Changing the default collation for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be a complex operation and involves the following steps:</span></span>  
  
-   <span data-ttu-id="bf3e8-108">Asegurarse de que se dispone de toda la información o scripts necesarios para volver a crear las bases de datos de usuario y todos los objetos contenidos en ellas.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-108">Make sure you have all the information or scripts needed to re-create your user databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="bf3e8-109">Exportar todos los datos mediante una herramienta como [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bf3e8-109">Export all your data using a tool such as the [bcp Utility](../../tools/bcp-utility.md).</span></span> <span data-ttu-id="bf3e8-110">Para obtener más información, vea [Importar y exportar datos en bloque &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bf3e8-110">For more information, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="bf3e8-111">Quitar todas las bases de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-111">Drop all the user databases.</span></span>  
  
-   <span data-ttu-id="bf3e8-112">Vuelva a generar la base de datos maestra al especificar la nueva intercalación en la propiedad SQLCOLLATION del comando **setup** .</span><span class="sxs-lookup"><span data-stu-id="bf3e8-112">Rebuild the master database specifying the new collation in the SQLCOLLATION property of the **setup** command.</span></span> <span data-ttu-id="bf3e8-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf3e8-113">For example:</span></span>  
  
    ```  
    Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName   
    /SQLSYSADMINACCOUNTS=accounts /[ SAPWD= StrongPassword ]   
    /SQLCOLLATION=CollationName  
    ```  
  
     <span data-ttu-id="bf3e8-114">Para obtener más información, vea [Volver a generar bases de datos del sistema](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="bf3e8-114">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="bf3e8-115">Crear todas las bases de datos y todos los objetos contenidos en ellas.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-115">Create all the databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="bf3e8-116">Importar todos los datos.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-116">Import all your data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf3e8-117">En lugar de cambiar la intercalación predeterminada de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede especificar una intercalación predeterminada para cada nueva base de datos que cree.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-117">Instead of changing the default collation of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can specify a default collation for each new database you create.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3e8-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf3e8-118">See Also</span></span>  
 <span data-ttu-id="bf3e8-119">[Compatibilidad con la intercalación y Unicode](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="bf3e8-119">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="bf3e8-120">[Establecer o cambiar la intercalación de base de datos](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="bf3e8-120">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 <span data-ttu-id="bf3e8-121">[Establecer o cambiar la intercalación de columnas](set-or-change-the-column-collation.md) </span><span class="sxs-lookup"><span data-stu-id="bf3e8-121">[Set or Change the Column Collation](set-or-change-the-column-collation.md) </span></span>  
 [<span data-ttu-id="bf3e8-122">Volver a generar bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="bf3e8-122">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
