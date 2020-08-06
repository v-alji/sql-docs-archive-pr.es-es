---
title: Conectar al servidor (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.dtsserver.f1
ms.assetid: 5be897bd-f36c-4c6a-a91a-13d0d016f8b6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8821018c45fdd77c4b3b896afc47b8f5b425af88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749453"
---
# <a name="connect-to-server-integration-services"></a><span data-ttu-id="b48fb-102">Conectar al servidor (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="b48fb-102">Connect to Server (Integration Services)</span></span>
  <span data-ttu-id="b48fb-103">Use este cuadro de diálogo para ver o especificar opciones cuando se conecte a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b48fb-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b48fb-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="b48fb-104">Options</span></span>  
 <span data-ttu-id="b48fb-105">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="b48fb-105">**Server type**</span></span>  
 <span data-ttu-id="b48fb-106">Al registrar un servidor desde el Explorador de objetos, seleccione el tipo de servidor al que conectarse: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services.</span><span class="sxs-lookup"><span data-stu-id="b48fb-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="b48fb-107">El resto del cuadro de diálogo muestra simplemente las opciones que se aplican al tipo de servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b48fb-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="b48fb-108">Cuando se registra un servidor desde Servidores registrados, el cuadro Tipo de servidor es de solo lectura y coincide con el tipo de servidor que se muestra en el componente Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b48fb-108">When registering a server from Registered Servers, the Server type box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="b48fb-109">Para registrar un tipo distinto de servidor, seleccione [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services desde la barra de herramientas Servidores registrados antes de comenzar a registrar un servidor nuevo.</span><span class="sxs-lookup"><span data-stu-id="b48fb-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="b48fb-110">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="b48fb-110">**Server name**</span></span>  
 <span data-ttu-id="b48fb-111">Seleccione el servidor al que va a conectarse.</span><span class="sxs-lookup"><span data-stu-id="b48fb-111">Select the server to connect to.</span></span> <span data-ttu-id="b48fb-112">De forma predeterminada, aparecerá la instancia de servidor a la que se ha conectado por última vez.</span><span class="sxs-lookup"><span data-stu-id="b48fb-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b48fb-113">No use *\<servername>* \\ *\<instancename>* , porque no [!INCLUDE[ssIS](../includes/ssis-md.md)] admite varias instancias en un equipo.</span><span class="sxs-lookup"><span data-stu-id="b48fb-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="b48fb-114">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="b48fb-114">**Authentication**</span></span>  
 <span data-ttu-id="b48fb-115">La autenticación [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows solo está disponible para [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b48fb-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="b48fb-116">Windows permite al usuario conectarse mediante una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="b48fb-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="b48fb-117">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="b48fb-117">**User name**</span></span>  
 <span data-ttu-id="b48fb-118">Esta opción no está disponible ya que la autenticación de Windows solo está disponible para [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b48fb-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="b48fb-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="b48fb-119">**Password**</span></span>  
 <span data-ttu-id="b48fb-120">Esta opción no está disponible ya que la autenticación de Windows solo está disponible para [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b48fb-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="b48fb-121">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="b48fb-121">**Connect**</span></span>  
 <span data-ttu-id="b48fb-122">Haga clic aquí para conectarse al servidor seleccionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b48fb-122">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="b48fb-123">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="b48fb-123">**Options**</span></span>  
 <span data-ttu-id="b48fb-124">Haga clic aquí para que se muestren las opciones adicionales de conexión al servidor, como registrar un servidor y recordar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b48fb-124">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
