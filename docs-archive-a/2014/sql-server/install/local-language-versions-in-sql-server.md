---
title: Versiones en idioma local en SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 20b99363-0490-4aa3-9a3d-262f827d81e8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646ffaed1e4b709c2c26030379f0a7f223f221e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744976"
---
# <a name="local-language-versions-in-sql-server"></a><span data-ttu-id="3d049-102">Versiones en idioma local en SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d049-102">Local Language Versions in SQL Server</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3d049-103">admite todos los idiomas compatibles con los sistemas operativos Windows.</span><span class="sxs-lookup"><span data-stu-id="3d049-103">supports all languages that are supported by Windows operating systems.</span></span>  
  
## <a name="cross-language-support"></a><span data-ttu-id="3d049-104">Compatibilidad entre idiomas</span><span class="sxs-lookup"><span data-stu-id="3d049-104">Cross-Language Support</span></span>  
  
-   <span data-ttu-id="3d049-105">La versión en inglés de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es compatible con todas las versiones traducidas de los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="3d049-105">The English-language version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is supported on all localized versions of operating systems.</span></span>  
  
-   <span data-ttu-id="3d049-106">Las versiones localizadas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son compatibles con los sistemas operativos con el idioma correspondiente o con las versiones en inglés de los sistemas operativos admitidos mediante la configuración del paquete de Interfaz de usuario multilingüe (MUI) de Windows.</span><span class="sxs-lookup"><span data-stu-id="3d049-106">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on localized operating systems with the corresponding language or on English-language versions of supported operating systems by using the Windows Multilingual User Interface Pack (MUI) settings.</span></span> <span data-ttu-id="3d049-107">Para más información, consulte [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span><span class="sxs-lookup"><span data-stu-id="3d049-107">For more information, see [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span></span>  
  
-   <span data-ttu-id="3d049-108">Las versiones localizadas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo se pueden actualizar a versiones localizadas del mismo idioma y no se pueden actualizar a la versión en inglés.</span><span class="sxs-lookup"><span data-stu-id="3d049-108">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can only be upgraded to localized versions of the same language, and cannot be upgraded to the English-language version.</span></span>  
  
-   <span data-ttu-id="3d049-109">Las versiones traducidas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] también se pueden instalar en paralelo con las instancias en inglés de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d049-109">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can also be installed side by side with English-language instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="configure-operating-system-to-support-localized-versions"></a><a name="BK_ConfigureOS"></a> <span data-ttu-id="3d049-110">Configure Operating System to Support Localized Versions</span><span class="sxs-lookup"><span data-stu-id="3d049-110">Configure Operating System to Support Localized Versions</span></span>  
 <span data-ttu-id="3d049-111">Las versiones traducidas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se admiten en las versiones en inglés de los sistemas operativos admitidos a través del uso de la configuración del paquete de Interfaz de usuario multilingüe (MUI) de Windows.</span><span class="sxs-lookup"><span data-stu-id="3d049-111">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on English-language versions of supported operating systems through the use of Windows Multilingual User Interface Pack (MUI) settings.</span></span>  
  
 <span data-ttu-id="3d049-112">No obstante, deberá comprobar algunas configuraciones del sistema operativo antes de instalar una versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un servidor que ejecute un sistema operativo en inglés con una configuración de MUI no en inglés.</span><span class="sxs-lookup"><span data-stu-id="3d049-112">However, you must verify certain operating system settings before installing a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a server that is running an English-language operating system with a non-English MUI setting.</span></span> <span data-ttu-id="3d049-113">Debe comprobar que las siguientes configuraciones del sistema operativo coinciden con el idioma de la versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vaya a instalar:</span><span class="sxs-lookup"><span data-stu-id="3d049-113">You need to verify that the following operating system settings match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed:</span></span>  
  
-   <span data-ttu-id="3d049-114">La configuración de la interfaz de usuario del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="3d049-114">The operating system user interface setting</span></span>  
  
-   <span data-ttu-id="3d049-115">La configuración regional de usuario del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="3d049-115">The operating system user locale setting</span></span>  
  
-   <span data-ttu-id="3d049-116">La configuración regional del sistema</span><span class="sxs-lookup"><span data-stu-id="3d049-116">The system locale setting</span></span>  
  
 <span data-ttu-id="3d049-117">Si la configuración no coincide con el idioma de la versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vaya a instalar, utilice los siguientes procedimientos para establecer correctamente esta configuración del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3d049-117">If the settings do not match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed, then use the following procedures to correctly set these operating system settings.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3d049-118">No se admite la instalación de versiones en distinto idioma de instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="3d049-118">Installations of different language versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances on the same computer are not supported.</span></span>  
  
#### <a name="to-change-the-operating-system-user-interface-setting"></a><span data-ttu-id="3d049-119">Para cambiar la configuración de la interfaz de usuario del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="3d049-119">To change the operating system user interface setting</span></span>  
  
1.  <span data-ttu-id="3d049-120">Si todavía no está instalada, instale la MUI del sistema operativo que coincide con la versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d049-120">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d049-121">En Panel de control, abra **Configuración regional y de idioma**.</span><span class="sxs-lookup"><span data-stu-id="3d049-121">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="3d049-122">En la pestaña **Idiomas** , seleccione para **Idioma usado en menús y cuadros de diálogo**, un valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="3d049-122">On the **Languages** tab, for **Language used in menus and dialogs**, select a value from the list.</span></span>  
  
     <span data-ttu-id="3d049-123">Este valor afectará al idioma de la interfaz de usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], por lo tanto deberá coincidir con la versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d049-123">This setting will affect the user interface language of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so it must match your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="3d049-124">Haga clic en **Aplicar** para confirmar el cambio y en **Aceptar** para cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="3d049-124">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-operating-system-user-locale-setting"></a><span data-ttu-id="3d049-125">Para cambiar la configuración regional de usuario del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="3d049-125">To change the operating system user locale setting</span></span>  
  
1.  <span data-ttu-id="3d049-126">Si todavía no está instalada, instale la MUI del sistema operativo que coincide con la versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d049-126">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d049-127">En Panel de control, abra **Configuración regional y de idioma**.</span><span class="sxs-lookup"><span data-stu-id="3d049-127">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="3d049-128">En la pestaña **Opciones regionales** , en **Seleccionar un elemento para que coincida con sus preferencias**, seleccione un valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="3d049-128">On the **Regional Options** tab, for **Select an item to match its preferences**, select a value from the list.</span></span>  
  
     <span data-ttu-id="3d049-129">Este valor afectará al formato de los datos específicos de una cultura.</span><span class="sxs-lookup"><span data-stu-id="3d049-129">This setting will affect culture-specific data formatting.</span></span>  
  
4.  <span data-ttu-id="3d049-130">Haga clic en **Aplicar** para confirmar el cambio y en **Aceptar** para cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="3d049-130">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-system-locale-setting"></a><span data-ttu-id="3d049-131">Para cambiar la configuración regional del sistema</span><span class="sxs-lookup"><span data-stu-id="3d049-131">To change the system locale setting</span></span>  
  
1.  <span data-ttu-id="3d049-132">Si todavía no está instalada, instale la MUI del sistema operativo que coincide con la versión traducida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d049-132">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d049-133">En Panel de control, abra **Configuración regional y de idioma**.</span><span class="sxs-lookup"><span data-stu-id="3d049-133">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="3d049-134">En la pestaña **Opciones avanzadas** , en **Select a language to match the language version of the non-Unicode programs you want to use**(Seleccione un idioma que coincida con la versión del idioma de los programas no Unicode que quiere usar), seleccione un valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="3d049-134">On the **Advanced** tab, for **Select a language to match the language version of the non-Unicode programs you want to use**, select a value from the list.</span></span>  
  
     <span data-ttu-id="3d049-135">Este valor permitirá que el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] elija la mejor intercalación predeterminada para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d049-135">This setting will allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to choose the best default collation for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
4.  <span data-ttu-id="3d049-136">Haga clic en **Aplicar** para confirmar el cambio y en **Aceptar** para cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="3d049-136">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d049-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d049-137">See Also</span></span>  
 <span data-ttu-id="3d049-138">[Requisitos de hardware y software para la instalación de SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3d049-138">[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 [<span data-ttu-id="3d049-139">Instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3d049-139">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
