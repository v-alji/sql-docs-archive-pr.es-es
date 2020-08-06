---
title: Nuevo o editar el registro de servidor (pestaña general) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.dts.f1
ms.assetid: b586b736-344b-4e42-83ee-96f66ad433a5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4968c3f98b8bab5b2e641e6fb1e30a6d682f9b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676652"
---
# <a name="new-or-edit-server-registration-general-tab-ssis"></a><span data-ttu-id="b801b-102">Nuevo o Editar propiedades de registro de servidor (pestaña General de SSIS)</span><span class="sxs-lookup"><span data-stu-id="b801b-102">New or Edit Server Registration (General Tab) (SSIS)</span></span>
  <span data-ttu-id="b801b-103">Utilice esta pestaña para especificar las opciones cuando se registra [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b801b-103">Use this tab to specify options when registering [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b801b-104">Para obtener acceso a esta página, en Servidores registrados, haga clic en **Integration Services** en la barra de herramientas de **Servidores registrados** , haga clic con el botón derecho en cualquier grupo de servidores registrados, seleccione **Nuevo**y, luego, haga clic en **Registro de servidor**.</span><span class="sxs-lookup"><span data-stu-id="b801b-104">To access this page, in Registered Servers, click **Integration Services** on the **Registered Servers** toolbar, right-click any registered servers group, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b801b-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="b801b-105">Options</span></span>  
 <span data-ttu-id="b801b-106">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="b801b-106">**Server type**</span></span>  
 <span data-ttu-id="b801b-107">Cuando registra un servidor en Servidores registrados, el cuadro **Tipo de servidor** es de solo lectura y corresponde al tipo de servidor que se muestra en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b801b-107">When a server is registered in Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in Registered Servers.</span></span> <span data-ttu-id="b801b-108">Para registrar un tipo diferente de servidor, haga clic en **Motor de base de datos**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition** o **Integration Services** en la barra de herramientas de **Servidores registrados** antes de iniciar el registro de un nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="b801b-108">To register a different type of server, click **Database Engine**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="b801b-109">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="b801b-109">**Server name**</span></span>  
 <span data-ttu-id="b801b-110">Seleccione el servidor con el que se va a establecer conexión.</span><span class="sxs-lookup"><span data-stu-id="b801b-110">Select the server to which to connect.</span></span> <span data-ttu-id="b801b-111">De forma predeterminada, aparecerá el servidor con el que se realizó la última conexión.</span><span class="sxs-lookup"><span data-stu-id="b801b-111">The server last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="b801b-112">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="b801b-112">**Authentication**</span></span>  
 <span data-ttu-id="b801b-113">El modo de autenticación de Windows permite al usuario conectarse mediante una cuenta de usuario de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="b801b-113">Windows Authentication mode allows a user to connect through a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="b801b-114">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="b801b-114">**User name**</span></span>  
 <span data-ttu-id="b801b-115">Esta opción no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="b801b-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="b801b-116">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="b801b-116">**Password**</span></span>  
 <span data-ttu-id="b801b-117">Esta opción no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="b801b-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="b801b-118">**Recordar contraseña**</span><span class="sxs-lookup"><span data-stu-id="b801b-118">**Remember password**</span></span>  
 <span data-ttu-id="b801b-119">Esta opción no está disponible en esta versión.</span><span class="sxs-lookup"><span data-stu-id="b801b-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="b801b-120">**Nombre del servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="b801b-120">**Registered server name**</span></span>  
 <span data-ttu-id="b801b-121">El nombre que quiere que aparezca en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="b801b-121">The name you want to appear in **Registered Servers**.</span></span> <span data-ttu-id="b801b-122">Este nombre no tiene que coincidir con el cuadro **Nombre del servidor** .</span><span class="sxs-lookup"><span data-stu-id="b801b-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="b801b-123">**Descripción del servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="b801b-123">**Registered server description**</span></span>  
 <span data-ttu-id="b801b-124">Escriba una descripción opcional del servidor.</span><span class="sxs-lookup"><span data-stu-id="b801b-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="b801b-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="b801b-125">**Test**</span></span>  
 <span data-ttu-id="b801b-126">Haga clic para probar la conexión al servidor seleccionado en **Nombre del servidor**.</span><span class="sxs-lookup"><span data-stu-id="b801b-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="b801b-127">**Guardar**</span><span class="sxs-lookup"><span data-stu-id="b801b-127">**Save**</span></span>  
 <span data-ttu-id="b801b-128">Haga clic en esta opción para guardar la configuración de Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b801b-128">Click to save the Registered Servers settings.</span></span>  
  
  
