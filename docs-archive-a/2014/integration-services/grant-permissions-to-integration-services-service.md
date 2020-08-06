---
title: Conceder permisos para Integration Services servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e7ab0c2f482e5a0b1bfeaa06f38ec5a886420a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663599"
---
# <a name="grant-permissions-to-integration-services-service"></a><span data-ttu-id="c7b62-102">Conceder permisos para el servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="c7b62-102">Grant Permissions to Integration Services Service</span></span>
  <span data-ttu-id="c7b62-103">En versiones anteriores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], cuando se instalaba [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] todos los usuarios del grupo Usuarios tenía acceso al servicio de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c7b62-103">In previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], by default when you installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all users in the Users group had access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="c7b62-104">Cuando instala la versión actual de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], los usuarios no tienen acceso al servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7b62-104">When you install the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], users do not have access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="c7b62-105">El servicio es seguro de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c7b62-105">The service is secure by default.</span></span> <span data-ttu-id="c7b62-106">Una vez instalado [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , el administrador debe conceder acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="c7b62-106">After [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed, the administrator must grant access to the service.</span></span>  
  
### <a name="to-grant-access-to-the-integration-services-service"></a><span data-ttu-id="c7b62-107">Para conceder acceso al servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="c7b62-107">To grant access to the Integration Services service</span></span>  
  
1.  <span data-ttu-id="c7b62-108">Ejecute Dcomcnfg.exe.</span><span class="sxs-lookup"><span data-stu-id="c7b62-108">Run Dcomcnfg.exe.</span></span> <span data-ttu-id="c7b62-109">Dcomcnfg.exe proporciona una interfaz de usuario para modificar algunos valores de configuración del Registro.</span><span class="sxs-lookup"><span data-stu-id="c7b62-109">Dcomcnfg.exe provides a user interface for modifying certain settings in the registry.</span></span>  
  
2.  <span data-ttu-id="c7b62-110">En el cuadro de diálogo **Servicios de componente**, expanda el nodo Servicios de componente > Equipos > Mi PC > Configuración DCOM.</span><span class="sxs-lookup"><span data-stu-id="c7b62-110">In the **Component Services** dialog, expand the Component Services > Computers > My Computer > DCOM Config node.</span></span>  
  
3.  <span data-ttu-id="c7b62-111">Haga clic con el botón secundario en **Microsoft SQL Server Integration Services 12,0**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c7b62-111">Right-click **Microsoft SQL Server Integration Services 12.0**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c7b62-112">En la pestaña **Seguridad** , haga clic en **Editar** en la sección **Permisos de inicio y activación** .</span><span class="sxs-lookup"><span data-stu-id="c7b62-112">On the **Security** tab, click **Edit** in the **Launch and Activation Permissions** area.</span></span>  
  
5.  <span data-ttu-id="c7b62-113">Agregue usuarios y asigne los permisos adecuados y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="c7b62-113">Add users and assign appropriate permissions, and then click Ok.</span></span>  
  
6.  <span data-ttu-id="c7b62-114">Repita los pasos 4 a 5 para los permisos de acceso.</span><span class="sxs-lookup"><span data-stu-id="c7b62-114">Repeat steps 4 - 5 for Access Permissions.</span></span>  
  
7.  <span data-ttu-id="c7b62-115">Reinicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c7b62-115">Restart SQL Server Management Studio.</span></span>  
  
8.  <span data-ttu-id="c7b62-116">Reinicie el Servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7b62-116">Restart the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Service.</span></span>  
  
  
