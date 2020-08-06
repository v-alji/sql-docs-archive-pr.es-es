---
title: Cuentas de dominio necesarias para la granja de servidores de SharePoint (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 90cd6d3e-a271-4cb8-81f2-fc555b2d3cab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7d180fbc12a264256156c878916838f7caeec723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677398"
---
# <a name="domain-accounts-required-for-sharepoint-farm-upgrade-advisor"></a><span data-ttu-id="3c50f-102">Cuentas de dominio necesarias para una granja de servidores de SharePoint (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="3c50f-102">Domain accounts required for SharePoint farm (Upgrade Advisor)</span></span>
  <span data-ttu-id="3c50f-103">Los productos de SharePoint que están configurados para un entorno de una granja requieren el uso de cuentas de dominio.</span><span class="sxs-lookup"><span data-stu-id="3c50f-103">SharePoint products that are configured for a farm environment require that you use domain accounts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="3c50f-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c50f-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="3c50f-105">Componente</span><span class="sxs-lookup"><span data-stu-id="3c50f-105">Component</span></span>  
 [!INCLUDE[ssRS](../../includes/ssrs.md)]  
  
### <a name="description"></a><span data-ttu-id="3c50f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c50f-106">Description</span></span>  
 <span data-ttu-id="3c50f-107">Los productos de SharePoint que se configuran para el entorno de una granja requieren el uso de cuentas de dominio para las conexiones a bases de datos y servicios.</span><span class="sxs-lookup"><span data-stu-id="3c50f-107">SharePoint products that are configured for a farm environment require that you use domain accounts for services and database connections.</span></span> <span data-ttu-id="3c50f-108">Esto incluye la cuenta que ha especificado para la cuenta de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="3c50f-108">This includes the account you have specified for the Reporting Services service account.</span></span>  
  
 <span data-ttu-id="3c50f-109">En las páginas de Administración central de SharePoint 2010 puede ver problemas si no utiliza una cuenta de usuario de dominio para Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="3c50f-109">SharePoint 2010 Central Administration pages are one place you will see problems if you are not using a domain user account for Reporting Services.</span></span> <span data-ttu-id="3c50f-110">Al intentar configurar la integración de Reporting Services, verá un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c50f-110">When you try to configure Reporting Services integration, you will see an error message similar to the following:</span></span>  
  
 <span data-ttu-id="3c50f-111">"El servidor de informes se está ejecutando en la cuenta de servicio NT AUTHORITY\NETWORK integrada, lo que no se admite en una instalación de granja de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c50f-111">"The report server is running under the built-in NT AUTHORITY\NETWORK SERVICE account, which is not supported by a SharePoint farm installation.</span></span> <span data-ttu-id="3c50f-112">Vuelva a configurar el servidor de informes para que se ejecute en una cuenta de dominio."</span><span class="sxs-lookup"><span data-stu-id="3c50f-112">Please reconfigure the report server to run under a domain account."</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3c50f-113">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="3c50f-113">Corrective Action</span></span>  
 <span data-ttu-id="3c50f-114">En [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y versiones anteriores, use el administrador de configuración de Reporting Services para cambiar la cuenta asignada como cuenta de servicio del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3c50f-114">For [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and previous versions, use the Reporting Services Configuration Manager to change the account that is assigned as the report server service account.</span></span>  
  
#### <a name="to-change-the-service-account-from-configuration-manager"></a><span data-ttu-id="3c50f-115">Para cambiar la cuenta de servicio del Administrador de configuración</span><span class="sxs-lookup"><span data-stu-id="3c50f-115">To change the service account from Configuration Manager</span></span>  
  
1.  <span data-ttu-id="3c50f-116">En el menú **Inicio** , seleccione **todos los programas**y, a continuación, haga clic en **Microsoft SQL Server 2008 R2**.</span><span class="sxs-lookup"><span data-stu-id="3c50f-116">From the **Start** menu, select **All Programs**, and then click **Microsoft SQL Server 2008 R2**.</span></span>  
  
2.  <span data-ttu-id="3c50f-117">Seleccione **herramientas de configuración**y, a continuación, haga clic en **Administrador de configuración de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="3c50f-117">Select **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="3c50f-118">En Configuration Manager, seleccione la pestaña **cuenta de servicio** .</span><span class="sxs-lookup"><span data-stu-id="3c50f-118">In Configuration Manager, select the **Service Account** tab.</span></span>  
  
4.  <span data-ttu-id="3c50f-119">Seleccione **usar otra cuenta** y escriba las credenciales de una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="3c50f-119">Select **Use another account** and enter the credentials for a domain account.</span></span>  
  
5.  <span data-ttu-id="3c50f-120">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3c50f-120">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c50f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c50f-121">See Also</span></span>  
 [<span data-ttu-id="3c50f-122">Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3c50f-122">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
  
  
