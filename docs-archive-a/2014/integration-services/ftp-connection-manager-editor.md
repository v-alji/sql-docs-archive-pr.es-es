---
title: Editor del administrador de conexiones FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftpconnectionmanager.f1
helpviewer_keywords:
- FTP Connection Manager Editor
ms.assetid: 874b6585-255b-4a43-8396-bb08c3e8ac2b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d14635a4d90c267801f6d372dda5c7bcc7f4869f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752265"
---
# <a name="ftp-connection-manager-editor"></a><span data-ttu-id="4d193-102">Editor del administrador de conexiones FTP</span><span class="sxs-lookup"><span data-stu-id="4d193-102">FTP Connection Manager Editor</span></span>
  <span data-ttu-id="4d193-103">Utilice el cuadro de diálogo **Editor del administrador de conexiones FTP** para especificar propiedades de conexión con un servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="4d193-103">Use the **FTP Connection Manager Editor** dialog box to specify properties for connecting to an FTP server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4d193-104">El administrador de conexiones FTP solo admite la autenticación anónima y la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="4d193-104">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="4d193-105">No es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4d193-105">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="4d193-106">Para obtener más información acerca del administrador de conexiones FTP, vea [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4d193-106">To learn more about the FTP connection manager, see [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d193-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="4d193-107">Options</span></span>  
 <span data-ttu-id="4d193-108">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="4d193-108">**Server name**</span></span>  
 <span data-ttu-id="4d193-109">Proporcione el nombre del servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="4d193-109">Provide the name of the FTP server.</span></span>  
  
 <span data-ttu-id="4d193-110">**Puerto de servidor**</span><span class="sxs-lookup"><span data-stu-id="4d193-110">**Server port**</span></span>  
 <span data-ttu-id="4d193-111">Especifique el número de puerto del servidor FTP que va a utilizar en la conexión.</span><span class="sxs-lookup"><span data-stu-id="4d193-111">Specify the port number on the FTP server to use for the connection.</span></span> <span data-ttu-id="4d193-112">El valor predeterminado de esta propiedad es **21**.</span><span class="sxs-lookup"><span data-stu-id="4d193-112">The default value of this property is **21**.</span></span>  
  
 <span data-ttu-id="4d193-113">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="4d193-113">**User name**</span></span>  
 <span data-ttu-id="4d193-114">Indique un nombre de usuario para tener acceso al servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="4d193-114">Provide a user name to access the FTP server.</span></span> <span data-ttu-id="4d193-115">El valor predeterminado de esta propiedad es **anonymous**.</span><span class="sxs-lookup"><span data-stu-id="4d193-115">The default value of this property is **anonymous**.</span></span>  
  
 <span data-ttu-id="4d193-116">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="4d193-116">**Password**</span></span>  
 <span data-ttu-id="4d193-117">Indique la contraseña para tener acceso al servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="4d193-117">Provide the password to access the FTP server.</span></span>  
  
 <span data-ttu-id="4d193-118">**Tiempo de espera (en segundos)**</span><span class="sxs-lookup"><span data-stu-id="4d193-118">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="4d193-119">Especifique el número de segundos que tarda la tarea en agotarse el tiempo de espera. Un valor de **0** indica una cantidad de tiempo infinita.</span><span class="sxs-lookup"><span data-stu-id="4d193-119">Specify the number of seconds the task takes before timing out. A value of **0** indicates an infinite amount of time.</span></span> <span data-ttu-id="4d193-120">El valor predeterminado de esta propiedad es **60**.</span><span class="sxs-lookup"><span data-stu-id="4d193-120">The default value of this property is **60**.</span></span>  
  
 <span data-ttu-id="4d193-121">**Usar modo pasivo**</span><span class="sxs-lookup"><span data-stu-id="4d193-121">**Use passive mode**</span></span>  
 <span data-ttu-id="4d193-122">Especifique si inicia la conexión el servidor o el cliente.</span><span class="sxs-lookup"><span data-stu-id="4d193-122">Specify whether the server or the client initiates the connection.</span></span> <span data-ttu-id="4d193-123">El servidor inicia la conexión en modo activo y el cliente en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="4d193-123">The server initiates the connection in active mode, and the client activates the connection in passive mode.</span></span> <span data-ttu-id="4d193-124">El valor predeterminado de esta propiedad es **active mode**.</span><span class="sxs-lookup"><span data-stu-id="4d193-124">The default value of this property is **active mode**.</span></span>  
  
 <span data-ttu-id="4d193-125">**Reintentos**</span><span class="sxs-lookup"><span data-stu-id="4d193-125">**Retries**</span></span>  
 <span data-ttu-id="4d193-126">Especifique el número de veces que la tarea intenta establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="4d193-126">Specify the number of times the task attempts to make a connection.</span></span> <span data-ttu-id="4d193-127">Un valor de **0** indica que no existe límite en el número de intentos.</span><span class="sxs-lookup"><span data-stu-id="4d193-127">A value of **0** indicates no limit to the number of attempts.</span></span>  
  
 <span data-ttu-id="4d193-128">**Tamaño del fragmento (en KB)**</span><span class="sxs-lookup"><span data-stu-id="4d193-128">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="4d193-129">Indique un tamaño de fragmento en kilobytes para transmitir datos.</span><span class="sxs-lookup"><span data-stu-id="4d193-129">Provide a chunk size in kilobytes for transmitting data.</span></span>  
  
 <span data-ttu-id="4d193-130">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="4d193-130">**Test Connection**</span></span>  
 <span data-ttu-id="4d193-131">Después de configurar el Administrador de conexiones FTP, haga clic en **Probar conexión**para confirmar que la conexión es viable.</span><span class="sxs-lookup"><span data-stu-id="4d193-131">After configuring the FTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d193-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d193-132">See Also</span></span>  
 [<span data-ttu-id="4d193-133">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="4d193-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
