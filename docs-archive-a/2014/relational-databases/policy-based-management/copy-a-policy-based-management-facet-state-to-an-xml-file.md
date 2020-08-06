---
title: Copia de en un archivo XML un estado de faceta de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745717"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a><span data-ttu-id="04dfc-102">Copiar en un archivo XML un estado de faceta de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="04dfc-102">Copy a Policy-Based Management Facet State to an XML File</span></span>
  <span data-ttu-id="04dfc-103">En este tema se describe cómo copiar el estado de una faceta de administración basada en directivas en un archivo XML en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04dfc-103">This topic describes how to how to copy the state of a Policy-Based Management facet to an XML file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="04dfc-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="04dfc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="04dfc-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="04dfc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="04dfc-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04dfc-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="04dfc-107">**Para copiar un estado de faceta en un archivo XML mediante:**</span><span class="sxs-lookup"><span data-stu-id="04dfc-107">**To copy a facet state to an XML file, using:**</span></span>  
  
     [<span data-ttu-id="04dfc-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04dfc-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="04dfc-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="04dfc-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="04dfc-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04dfc-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="04dfc-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="04dfc-111">Permissions</span></span>  
 <span data-ttu-id="04dfc-112">Los procedimientos descritos en este tema requieren la pertenencia al rol PolicyAdministratorRole de la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="04dfc-112">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="04dfc-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04dfc-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a><span data-ttu-id="04dfc-114">Para copiar un estado de faceta en un archivo XML</span><span class="sxs-lookup"><span data-stu-id="04dfc-114">To copy a facet state to an XML file</span></span>  
  
1.  <span data-ttu-id="04dfc-115">En el Explorador de objetos, haga clic con el botón derecho en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], objeto de instancia, base de datos u objeto de base de datos y, después, haga clic en **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="04dfc-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="04dfc-116">En el cuadro de diálogo **Ver facetas -**_nombre_de_objeto_, haga clic en **Exportar estado actual como directiva**.</span><span class="sxs-lookup"><span data-stu-id="04dfc-116">In the **View Facets -**_object_name_ dialog box, click **Export Current State as Policy**.</span></span>  
  
3.  <span data-ttu-id="04dfc-117">En el cuadro de diálogo **Exportar como directiva** , escriba la ruta de acceso y el nombre del archivo, o use el botón Examinar (**...**) para buscar el archivo y, después, escriba el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="04dfc-117">In the **Export as Policy** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the file, and then type the name of the XML file.</span></span> <span data-ttu-id="04dfc-118">Para obtener más información acerca de las opciones disponibles en este cuadro de diálogo, vea [Export As Policy Dialog Box](export-as-policy-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="04dfc-118">For more information on the available options in this dialog box, see [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span></span>  
  
4.  <span data-ttu-id="04dfc-119">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04dfc-119">When finished, click **OK**.</span></span>  
  
  
