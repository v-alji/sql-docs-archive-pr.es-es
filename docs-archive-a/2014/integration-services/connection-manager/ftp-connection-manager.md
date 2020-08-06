---
title: Administrador de conexiones FTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FTP connection manager
- connections [Integration Services], FTP
- connection managers [Integration Services], FTP
ms.assetid: c4f43455-29ca-44ba-ac7f-ea729b1daf93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a402f399ba4b7e69fc1d3cbca9dd64b32217ced1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744817"
---
# <a name="ftp-connection-manager"></a><span data-ttu-id="0816e-102">FTP, administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="0816e-102">FTP Connection Manager</span></span>
  <span data-ttu-id="0816e-103">Un administrador de conexiones FTP habilita un paquete para conectarse a un servidor de Protocolo de transferencia de archivos (FTP).</span><span class="sxs-lookup"><span data-stu-id="0816e-103">An FTP connection manager enables a package to connect to a File Transfer Protocol (FTP) server.</span></span> <span data-ttu-id="0816e-104">La tarea FTP que incluye [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa este administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="0816e-104">The FTP task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="0816e-105">Cuando agrega un Administrador de conexiones FTP a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se puede resolver como una conexión FTP en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="0816e-105">When you add an FTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that can be resolved as an FTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="0816e-106">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `FTP`.</span><span class="sxs-lookup"><span data-stu-id="0816e-106">The `ConnectionManagerType` property of the connection manager is set to `FTP`.</span></span>  
  
 <span data-ttu-id="0816e-107">Puede configurar el administrador de conexiones FTP de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="0816e-107">You can configure the FTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="0816e-108">Especificar un nombre de servidor y puerto de servidor.</span><span class="sxs-lookup"><span data-stu-id="0816e-108">Specify a server name and server port.</span></span>  
  
-   <span data-ttu-id="0816e-109">Especificar un acceso anónimo, o proporcionar un nombre de usuario y una contraseña para la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="0816e-109">Specify anonymous access, or provide a user name and a password for basic authentication.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0816e-110">El administrador de conexiones FTP solo admite la autenticación anónima y la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="0816e-110">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="0816e-111">No es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0816e-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="0816e-112">Establecer el tiempo de espera, el número de reintentos y la cantidad de datos que se pueden copiar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="0816e-112">Set the time-out, number of retries, and the amount of data to copy at a time.</span></span>  
  
-   <span data-ttu-id="0816e-113">Indicar si el administrador de conexiones FTP usa el modo pasivo o activo.</span><span class="sxs-lookup"><span data-stu-id="0816e-113">Indicate whether the FTP connection manager uses passive or active mode.</span></span>  
  
 <span data-ttu-id="0816e-114">Según la configuración del sitio FTP al que se conecta el administrador de conexiones FTP, es posible que necesite cambiar los siguientes valores predeterminados del administrador de conexiones:</span><span class="sxs-lookup"><span data-stu-id="0816e-114">Depending on the configuration of the FTP site to which the FTP connection manager connects, you may need to change the following default values of the connection manager:</span></span>  
  
-   <span data-ttu-id="0816e-115">El puerto del servidor se establece en 21.</span><span class="sxs-lookup"><span data-stu-id="0816e-115">The server port is set to 21.</span></span> <span data-ttu-id="0816e-116">Debe especificar el puerto que escucha el sitio FTP.</span><span class="sxs-lookup"><span data-stu-id="0816e-116">You should specify the port that the FTP site listens to.</span></span>  
  
-   <span data-ttu-id="0816e-117">El nombre del usuario se establece en "anónimo".</span><span class="sxs-lookup"><span data-stu-id="0816e-117">The user name is set to "anonymous".</span></span> <span data-ttu-id="0816e-118">Debe proporcionar las credenciales que requiere el sitio FTP.</span><span class="sxs-lookup"><span data-stu-id="0816e-118">You should provide the credentials that the FTP site requires.</span></span>  
  
## <a name="activepassive-modes"></a><span data-ttu-id="0816e-119">Modos activo/pasivo</span><span class="sxs-lookup"><span data-stu-id="0816e-119">Active/Passive Modes</span></span>  
 <span data-ttu-id="0816e-120">Un administrador de conexiones FTP puede enviar y recibir archivos con el modo activo o modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="0816e-120">An FTP connection manager can send and receive files using either active mode or passive mode.</span></span> <span data-ttu-id="0816e-121">En el modo activo, el servidor inicia la conexión de datos, mientras que en el modo pasivo, la inicia el cliente.</span><span class="sxs-lookup"><span data-stu-id="0816e-121">In active mode, the server initiates the data connection, and in passive mode, the client initiates the data connection.</span></span>  
  
## <a name="configuration-of-the-ftp-connection-manager"></a><span data-ttu-id="0816e-122">Configuración del administrador de conexiones FTP</span><span class="sxs-lookup"><span data-stu-id="0816e-122">Configuration of the FTP Connection Manager</span></span>  
 <span data-ttu-id="0816e-123">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0816e-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="0816e-124">Para obtener información sobre las propiedades que se pueden configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Editor del administrador de conexiones FTP](../ftp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="0816e-124">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [FTP Connection Manager Editor](../ftp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="0816e-125">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="0816e-125">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0816e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0816e-126">See Also</span></span>  
 <span data-ttu-id="0816e-127">[Tarea FTP](../control-flow/ftp-task.md) </span><span class="sxs-lookup"><span data-stu-id="0816e-127">[FTP Task](../control-flow/ftp-task.md) </span></span>  
 [<span data-ttu-id="0816e-128">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0816e-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
