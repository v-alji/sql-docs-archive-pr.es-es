---
title: Exportar una directiva de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 15f554aeeebfd47c3fa1ea13b100fbe6bcfcc055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673662"
---
# <a name="export-a-policy-based-management-policy"></a><span data-ttu-id="634cb-102">Exportar una directiva de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="634cb-102">Export a Policy-Based Management Policy</span></span>
  <span data-ttu-id="634cb-103">En este tema se describe cómo exportar una directiva de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="634cb-103">This topic describes how to export a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="634cb-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="634cb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="634cb-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="634cb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="634cb-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="634cb-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="634cb-107">**Para exportar una directiva mediante:**</span><span class="sxs-lookup"><span data-stu-id="634cb-107">**To export a policy, using:**</span></span>  
  
     [<span data-ttu-id="634cb-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="634cb-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="634cb-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="634cb-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="634cb-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="634cb-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="634cb-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="634cb-111">Permissions</span></span>  
 <span data-ttu-id="634cb-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="634cb-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="634cb-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="634cb-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-export-a-policy"></a><span data-ttu-id="634cb-114">Para exportar una directiva</span><span class="sxs-lookup"><span data-stu-id="634cb-114">To export a policy</span></span>  
  
1.  <span data-ttu-id="634cb-115">En el Explorador de objetos, haga clic en el signo más para expandir el servidor que contiene la directiva de administración basada en directivas que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="634cb-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to export.</span></span>  
  
2.  <span data-ttu-id="634cb-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="634cb-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="634cb-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="634cb-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="634cb-118">Haga clic en el signo más para expandir la carpeta **Directivas** .</span><span class="sxs-lookup"><span data-stu-id="634cb-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="634cb-119">Haga clic con el botón derecho en la directiva que quiera exportar y seleccione **Exportar directiva**.</span><span class="sxs-lookup"><span data-stu-id="634cb-119">Right-click the policy that you want to export and select **Export Policy**.</span></span>  
  
6.  <span data-ttu-id="634cb-120">En el cuadro de diálogo **Exportar directiva** , escriba la ruta de acceso y el nombre del archivo en la barra de direcciones.</span><span class="sxs-lookup"><span data-stu-id="634cb-120">In the **Export Policy** dialog box, type the path and name of the file in the address bar.</span></span> <span data-ttu-id="634cb-121">También puede buscar una ubicación adecuada para el archivo en el panel de navegación del cuadro de diálogo, y escribir el nombre del archivo XML en el cuadro **Nombre de archivo** .</span><span class="sxs-lookup"><span data-stu-id="634cb-121">Alternately, find a suitable location for the file in the dialog box's navigation pane, and then type the name of the XML file in the **File Name** box.</span></span>  
  
7.  <span data-ttu-id="634cb-122">Cuando termine, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="634cb-122">When finished, click **Save**.</span></span>  
  
  
