---
title: Habilitar la opción Bloquear páginas en la memoria (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Lock Pages in Memory option
ms.assetid: cd581fbc-4747-439e-87f9-2f18e39c5bb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13290940c3a94a7ba79582d892a5e28670f24b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673268"
---
# <a name="enable-the-lock-pages-in-memory-option-windows"></a><span data-ttu-id="5f217-102">Habilitar la opción Bloquear páginas en la memoria (Windows)</span><span class="sxs-lookup"><span data-stu-id="5f217-102">Enable the Lock Pages in Memory Option (Windows)</span></span>
  <span data-ttu-id="5f217-103">Esta directiva de Windows determina qué cuentas pueden usar un proceso para mantener los datos en la memoria física, impidiendo que el sistema realice la paginación de los datos en la memoria virtual del disco.</span><span class="sxs-lookup"><span data-stu-id="5f217-103">This Windows policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f217-104">El bloqueo de páginas en memoria puede aumentar el rendimiento cuando se espera paginación de memoria en disco.</span><span class="sxs-lookup"><span data-stu-id="5f217-104">Locking pages in memory may boost performance when paging memory to disk is expected.</span></span>  
  
 <span data-ttu-id="5f217-105">Use la herramienta Directiva de grupo de Windows (gpedit.msc) para habilitar esta directiva para la cuenta usada por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f217-105">Use the Windows Group Policy tool (gpedit.msc) to enable this policy for the account used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5f217-106">Debe ser el administrador del sistema para cambiar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="5f217-106">You must be a system administrator to change this policy.</span></span>  
  
### <a name="to-enable-the-lock-pages-in-memory-option"></a><span data-ttu-id="5f217-107">Para habilitar la opción de bloqueo de páginas en memoria</span><span class="sxs-lookup"><span data-stu-id="5f217-107">To enable the lock pages in memory option</span></span>  
  
1.  <span data-ttu-id="5f217-108">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5f217-108">On the **Start** menu, click **Run**.</span></span> <span data-ttu-id="5f217-109">En el cuadro **abrir** , escriba `gpedit.msc` .</span><span class="sxs-lookup"><span data-stu-id="5f217-109">In the **Open** box, type `gpedit.msc`.</span></span>  
  
2.  <span data-ttu-id="5f217-110">En la consola **Editor de directivas de grupo local** , expanda **Configuración del equipo**y, a continuación, expanda **Configuración de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5f217-110">On the **Local Group Policy Editor** console, expand **Computer Configuration**, and then expand **Windows Settings**.</span></span>  
  
3.  <span data-ttu-id="5f217-111">Expanda **Configuración de seguridad**y, a continuación, expanda **Directivas locales**.</span><span class="sxs-lookup"><span data-stu-id="5f217-111">Expand **Security Settings**, and then expand **Local Policies**.</span></span>  
  
4.  <span data-ttu-id="5f217-112">Seleccione la carpeta **Asignación de derechos de usuario** .</span><span class="sxs-lookup"><span data-stu-id="5f217-112">Select the **User Rights Assignment** folder.</span></span>  
  
     <span data-ttu-id="5f217-113">Las directivas se mostrarán en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="5f217-113">The policies will be displayed in the details pane.</span></span>  
  
5.  <span data-ttu-id="5f217-114">En el panel, haga doble clic en **Bloquear páginas en la memoria**.</span><span class="sxs-lookup"><span data-stu-id="5f217-114">In the pane, double-click **Lock pages in memory**.</span></span>  
  
6.  <span data-ttu-id="5f217-115">En el cuadro de diálogo **Configuración de seguridad local: Bloquear páginas en memoria**, haga clic en **Agregar usuario o grupo**.</span><span class="sxs-lookup"><span data-stu-id="5f217-115">In the **Local Security Setting - Lock pages in memory** dialog box, click **Add User or Group**.</span></span>  
  
7.  <span data-ttu-id="5f217-116">En el cuadro de diálogo **Seleccionar usuarios, cuentas de servicio o grupos** , agregue una cuenta con privilegios para ejecutar sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="5f217-116">In the **Select Users, Service Accounts, or Groups** dialog box, add an account with privileges to run sqlservr.exe.</span></span>  
  
8.  <span data-ttu-id="5f217-117">Cierre sesión y vuelva a iniciarla para que este cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="5f217-117">Log out and then log back in for this change to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f217-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f217-118">See Also</span></span>  
 [<span data-ttu-id="5f217-119">Opciones de configuración de memoria del servidor</span><span class="sxs-lookup"><span data-stu-id="5f217-119">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  
