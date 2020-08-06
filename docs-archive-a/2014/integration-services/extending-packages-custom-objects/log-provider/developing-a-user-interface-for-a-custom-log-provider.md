---
title: Desarrollar una interfaz de usuario para un proveedor de registro personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom user interface [Integration Services], custom log providers
- custom log providers [Integration Services], developing custom user interface
ms.assetid: 6fd2d269-d87a-4134-82a1-40a09b3b5453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c3ce6cf5ad744e307bbb049347047bf94fc5a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663632"
---
# <a name="developing-a-user-interface-for-a-custom-log-provider"></a><span data-ttu-id="e3634-102">Desarrollar una interfaz de usuario para un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="e3634-102">Developing a User Interface for a Custom Log Provider</span></span>
  <span data-ttu-id="e3634-103">Muchos proveedores de registro de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tienen una interfaz de usuario personalizada que implementa <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> y reemplaza el cuadro de texto **Configuración** en el cuadro de diálogo **Configurar registros de SSIS** por una lista desplegable filtrada de administradores de conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="e3634-103">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="e3634-104">Sin embargo, las interfaces de usuario personalizadas para los proveedores de registro personalizados no se implementan en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3634-104">However, custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
<span data-ttu-id="e3634-105">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e3634-105">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e3634-106">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="e3634-106">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e3634-107">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="e3634-107">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e3634-108">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="e3634-108">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3634-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3634-109">See Also</span></span>  
 <span data-ttu-id="e3634-110">[Crear un proveedor de registro personalizado](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e3634-110">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="e3634-111">Codificar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="e3634-111">Coding a Custom Log Provider</span></span>](coding-a-custom-log-provider.md)  
  
  
