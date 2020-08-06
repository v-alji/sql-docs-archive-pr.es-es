---
title: Reparación de una instalación de Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675138"
---
# <a name="repair-a-distributed-replay-installation"></a><span data-ttu-id="0c864-102">Reparar una instalación de Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="0c864-102">Repair a Distributed Replay Installation</span></span>
  <span data-ttu-id="0c864-103">La reparación de un componente de Distributed Replay (controlador o cliente) hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c864-103">Repairing a Distributed Replay component (controller or client) will do the following:</span></span>  
  
1.  <span data-ttu-id="0c864-104">Instale todos los archivos asociados en el disco de nuevo y reemplace los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="0c864-104">Install all associated files on disk again, and replace any existing files.</span></span>  
  
2.  <span data-ttu-id="0c864-105">Volver a crear la cuenta de servicio de Windows si la cuenta de servicio correspondiente se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="0c864-105">Recreate the Windows service account if the corresponding service account was removed.</span></span>  
  
 <span data-ttu-id="0c864-106">No puede utilizar la operación de reparación para agregar o quitar componentes.</span><span class="sxs-lookup"><span data-stu-id="0c864-106">You cannot use the Repair operation to add or remove components.</span></span> <span data-ttu-id="0c864-107">Para agregar o quitar componentes, active o desactive el componente correspondiente en el árbol de características de la página **Selección de características** del programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c864-107">To add or remove components, check or uncheck the corresponding component in the Feature tree on the **Feature Selection** page in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a><span data-ttu-id="0c864-108">Para reparar una instalación de Distributed Replay con errores</span><span class="sxs-lookup"><span data-stu-id="0c864-108">To repair a failed installation of Distributed Replay</span></span>  
  
1.  <span data-ttu-id="0c864-109">En el menú **Inicio** , haga clic en **Panel de control**y haga doble clic en **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="0c864-109">From the **Start** menu, click **Control Panel**, and then double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="0c864-110">Seleccione [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en la ventana **Desinstalar o  cambiar un programa** y, a continuación, en el cuadro de diálogo [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , haga clic en **Reparar**.</span><span class="sxs-lookup"><span data-stu-id="0c864-110">Select [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in the **Uninstall or change a program** window, and then in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialog box, click **Repair**.</span></span>  
  
3.  <span data-ttu-id="0c864-111">Siga los pasos del asistente para la instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] y, en la página **Seleccionar características** , seleccione los componentes de Distributed Replay que desea reparar. A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c864-111">Follow the steps in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wizard, and on the **Select Features** page, select the Distributed Replay components you want to repair, and then click **Next.**.</span></span>  
  
4.  <span data-ttu-id="0c864-112">Complete el Asistente para la instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para reparar las características de Distributed Replay seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="0c864-112">Complete the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installation Wizard to repair the selected Distributed Replay features.</span></span>  
  
  
