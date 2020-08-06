---
title: Autenticación en modo de Reporting Services SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade SharePoint Mode [Reporting Services]
- SharePoint integration
- SharePoint Mode
ms.assetid: 2c19794a-dd55-4fe5-b901-6dd93e9f6beb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3b1316a1a49726ab0754f39160125425fec116d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748508"
---
# <a name="reporting-services-sharepoint-mode-authentication"></a><span data-ttu-id="3d1ed-102">Autenticación del modo de SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3d1ed-102">Reporting Services SharePoint Mode Authentication</span></span>
  <span data-ttu-id="3d1ed-103">Use la página **Autenticación del modo de SharePoint de Reporting Services** del Asistente para la instalación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para especificar las credenciales de la cuenta de servicio que se usa en la instalación actual de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d1ed-103">Use the **Reporting Services SharePoint Mode Authentication** page of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the credentials of the service account that is used in the current [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="3d1ed-104">Las credenciales se usarán para crear un nuevo grupo de aplicaciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-104">The credentials will be used to create a new SharePoint application pool.</span></span> <span data-ttu-id="3d1ed-105">Además, se creará una nueva aplicación de servicio de SharePoint para [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d1ed-105">Also, one new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint service application will be created.</span></span> <span data-ttu-id="3d1ed-106">El nombre de la aplicación de servicio contendrá el nombre de la instancia anterior de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d1ed-106">The service application name will contain the name of the previous [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3d1ed-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="3d1ed-107">Options</span></span>  
  
-   <span data-ttu-id="3d1ed-108">La opción **Nombre de la cuenta del grupo de aplicaciones SSRS** es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-108">The **SSRS Application Pool Account Name:** option is read only.</span></span> <span data-ttu-id="3d1ed-109">El valor se rellena automáticamente con el valor actual de la instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] existente que va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-109">The value is automatically populated with the current value from the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that you are upgrading.</span></span>  
  
-   <span data-ttu-id="3d1ed-110">La opción **Contraseña de la cuenta del grupo de aplicaciones SSRS** estará deshabilitada si la cuenta del grupo de aplicaciones no requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-110">The **SSRS Application Pool Account Password:** option will be disabled if the application pool account does not require a password.</span></span> <span data-ttu-id="3d1ed-111">Por ejemplo, "NT Authority\NetworkService".</span><span class="sxs-lookup"><span data-stu-id="3d1ed-111">For example, "NT Authority\NetworkService".</span></span> <span data-ttu-id="3d1ed-112">Si la cuenta del grupo de aplicaciones requiere una contraseña, no podrá continuar con la actualización hasta que escriba la contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-112">If the application pool account does require a password, you cannot continue with upgrade until you type the correct password.</span></span>  
  
 <span data-ttu-id="3d1ed-113">Para obtener más información, vea [actualizar y migrar Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) ( https://go.microsoft.com/fwlink/?LinkID=245628) .</span><span class="sxs-lookup"><span data-stu-id="3d1ed-113">For more information, see [Upgrade and Migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) (https://go.microsoft.com/fwlink/?LinkID=245628).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1ed-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d1ed-114">See Also</span></span>  
 [<span data-ttu-id="3d1ed-115">Actualizar y migrar Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3d1ed-115">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkID=245628)  
  
  
