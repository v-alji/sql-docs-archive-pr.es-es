---
title: Administrador de conexiones de SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 06b166a1-a9df-48ea-a0e8-9b8d6979c0a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3bb32c4895c6ec8fbcf31d57e8685c74de32dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669806"
---
# <a name="sap-bw-connection-manager"></a><span data-ttu-id="cd50a-102">Administrador de conexiones de SAP BW</span><span class="sxs-lookup"><span data-stu-id="cd50a-102">SAP BW Connection Manager</span></span>
  <span data-ttu-id="cd50a-103">El administrador de conexiones de SAP BW es el componente del administrador de conexiones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cd50a-103">The SAP BW connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="cd50a-104">Por tanto, el administrador de conexiones de SAP BW proporciona conectividad a un sistema SAP Netweaver BW versión 7 que necesitan los componentes de destino y de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cd50a-104">Thus, the SAP BW connection manager provides the connectivity to an SAP Netweaver BW version 7 system that the source and destination components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW need.</span></span> <span data-ttu-id="cd50a-105">(El origen y el destino de SAP BW que forman parte del paquete de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW son los únicos componentes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que usan el administrador de conexiones de SAP BW).</span><span class="sxs-lookup"><span data-stu-id="cd50a-105">(The SAP BW source and destination that are part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package are the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components that use the SAP BW connection manager.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd50a-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="cd50a-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="cd50a-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="cd50a-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="cd50a-108">Cuando agrega un administrador de conexiones de SAP BW a un paquete, la propiedad `ConnectionManagerType` del administrador de conexiones se establece en `SAPBI`.</span><span class="sxs-lookup"><span data-stu-id="cd50a-108">When you add an SAP BW connection manager to a package, the `ConnectionManagerType` property of the connection manager is set to `SAPBI`.</span></span>  
  
## <a name="configuring-the-sap-bw-connection-manager"></a><span data-ttu-id="cd50a-109">Configurar el administrador de conexiones de SAP BW</span><span class="sxs-lookup"><span data-stu-id="cd50a-109">Configuring the SAP BW Connection Manager</span></span>  
 <span data-ttu-id="cd50a-110">Puede configurar el administrador de conexiones de SAP BW de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd50a-110">You can configure the SAP BW connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="cd50a-111">Facilite el cliente, el nombre de usuario, la contraseña y el idioma de la conexión.</span><span class="sxs-lookup"><span data-stu-id="cd50a-111">Provide the client, user name, password, and language for the connection.</span></span>  
  
-   <span data-ttu-id="cd50a-112">Elija si desea conectarse a un único servidor de aplicaciones o un grupo de servidores con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="cd50a-112">Choose whether to connect to a single application server or to a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="cd50a-113">Proporcione el número de host y del sistema para un único servidor de aplicaciones o proporcione el servidor de mensajes, grupo y SID de un grupo de servidores con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="cd50a-113">Provide the host and system number for a single application server, or provide the message server, group, and SID for a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="cd50a-114">Habilite el registro personalizado de llamadas a funciones RFC para los componentes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cd50a-114">Enable custom logging of RFC function calls for the components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="cd50a-115">(Este registro es independiente del registro opcional que puede habilitar en los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ). Para habilitar el registro de las llamadas a funciones RFC, debe especificar un directorio en el que almacenar los archivos de registro que se crean antes y después de cada llamada a funciones RFC.</span><span class="sxs-lookup"><span data-stu-id="cd50a-115">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) To enable logging of RFC function calls, you specify a directory in which to store the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="cd50a-116">(Esta característica de registro crea múltiples archivos de registro en formato XML.</span><span class="sxs-lookup"><span data-stu-id="cd50a-116">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="cd50a-117">Dado que estos archivos de registro también contienen todas las filas de datos que se transfieren, es posible que los archivos de registro consuman gran cantidad de espacio en disco). Si no selecciona un directorio de registro, el registro no estará habilitado.</span><span class="sxs-lookup"><span data-stu-id="cd50a-117">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.) If you do not select a log directory, logging is not enabled.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="cd50a-118">Si los datos que se transfieren contienen información confidencial, los archivos de registro también contendrán esa información confidencial.</span><span class="sxs-lookup"><span data-stu-id="cd50a-118">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
-   <span data-ttu-id="cd50a-119">Use los valores especificados para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="cd50a-119">Use the values that you have entered to test the connection.</span></span>  
  
 <span data-ttu-id="cd50a-120">Si no conoce todos los valores necesarios para configurar el administrador de conexiones, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="cd50a-120">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="cd50a-121">Para obtener instrucciones sobre cómo configurar y utilizar el administrador de conexiones, el origen y el destino de SAP BW, vea las notas del producto, [Usar SQL Server 2008 Integration Services con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="cd50a-121">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="cd50a-122">Estas notas del producto también muestran cómo configurar los objetos necesarios en SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cd50a-122">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="cd50a-123">Usar el Diseñador SSIS para configurar el origen</span><span class="sxs-lookup"><span data-stu-id="cd50a-123">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="cd50a-124">Para obtener más información sobre las propiedades del administrador de conexiones de SAP BW que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd50a-124">For more information about the properties of the SAP BW connection manager that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="cd50a-125">Editor del administrador de conexiones SAP BW</span><span class="sxs-lookup"><span data-stu-id="cd50a-125">SAP BW Connection Manager Editor</span></span>](../sap-bw-connection-manager-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="cd50a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd50a-126">See Also</span></span>  
 [<span data-ttu-id="cd50a-127">Componentes de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="cd50a-127">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
