---
title: Importar una directiva de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d83ed589e147c61b1692447aacb17535f18a5c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663446"
---
# <a name="import-a-policy-based-management-policy"></a><span data-ttu-id="6aa94-102">Importar una directiva de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="6aa94-102">Import a Policy-Based Management Policy</span></span>
  <span data-ttu-id="6aa94-103">En este tema se describe cómo importar una instancia de directiva de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aa94-103">This topic describes how to import a Policy-Based Management policy instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6aa94-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6aa94-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6aa94-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6aa94-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6aa94-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6aa94-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6aa94-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6aa94-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6aa94-108">**Para importar una instancia de directiva mediante:**</span><span class="sxs-lookup"><span data-stu-id="6aa94-108">**To import a policy instance, using:**</span></span>  
  
     [<span data-ttu-id="6aa94-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aa94-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6aa94-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6aa94-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6aa94-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6aa94-111">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6aa94-112">se distribuye con directivas que se pueden utilizar para supervisar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aa94-112">ships with policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6aa94-113">De forma predeterminada, estas directivas no se instalan en [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], pero se pueden importar desde la ubicación predeterminada de C:\Archivos de programa\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="6aa94-113">By default, these policies are not installed on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], but they can be imported from the default location of C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6aa94-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6aa94-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6aa94-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="6aa94-115">Permissions</span></span>  
 <span data-ttu-id="6aa94-116">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="6aa94-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6aa94-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aa94-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-import-a-policy-instance"></a><span data-ttu-id="6aa94-118">Para importar una instancia de directiva</span><span class="sxs-lookup"><span data-stu-id="6aa94-118">To import a policy instance</span></span>  
  
1.  <span data-ttu-id="6aa94-119">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en que residirá la instancia de directiva recién importada.</span><span class="sxs-lookup"><span data-stu-id="6aa94-119">In **Object Explorer**, click the plus sign to expand the server where the newly-imported policy instance will reside.</span></span>  
  
2.  <span data-ttu-id="6aa94-120">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="6aa94-120">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="6aa94-121">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-121">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="6aa94-122">Haga clic con el botón derecho en la carpeta **Directivas** y seleccione **Importar directiva**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-122">Right-click the **Policies** folder and select **Import Policy**.</span></span>  
  
5.  <span data-ttu-id="6aa94-123">En el cuadro de diálogo **Importar** , escriba la ruta de acceso y el nombre del archivo, o use el botón Examinar ( **...** ) para buscar el archivo XML que contiene la directiva y, después, seleccione el archivo.</span><span class="sxs-lookup"><span data-stu-id="6aa94-123">In the **Import** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the XML file that contains the policy, and then select the file.</span></span> <span data-ttu-id="6aa94-124">Para obtener más información acerca de las opciones disponibles en el cuadro de diálogo **Importar** , vea [Import Policies Dialog Box](import-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="6aa94-124">For more information on the available options in the **Import** dialog box, see [Import Policies Dialog Box](import-policies-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="6aa94-125">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-125">When finished, click **OK**.</span></span>  
  
  
