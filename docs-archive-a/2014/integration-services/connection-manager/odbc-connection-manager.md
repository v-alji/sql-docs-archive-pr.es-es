---
title: Administrador de conexiones ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1069e31f3f8ffaf14dde091d913ff6d9f8fa7cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671626"
---
# <a name="odbc-connection-manager"></a><span data-ttu-id="58a07-102">ODBC, administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="58a07-102">ODBC Connection Manager</span></span>
  <span data-ttu-id="58a07-103">Un administrador de conexiones ODBC habilita un paquete para conectarse a una serie de sistemas de administración de bases de datos mediante la especificación Conectividad abierta de bases de datos (ODBC).</span><span class="sxs-lookup"><span data-stu-id="58a07-103">An ODBC connection manager enables a package to connect to a variety of database management systems using the Open Database Connectivity specification (ODBC).</span></span>  
  
 <span data-ttu-id="58a07-104">Cuando agrega una conexión ODBC a un paquete y establece las propiedades del administrador de conexiones, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones y agrega el administrador de conexiones a la `Connections` colección del paquete.</span><span class="sxs-lookup"><span data-stu-id="58a07-104">When you add an ODBC connection to a package and set the connection manager properties, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager and adds the connection manager to the `Connections` collection of the package.</span></span> <span data-ttu-id="58a07-105">En el tiempo de ejecución el administrador de conexiones se resuelve como una conexión ODBC física.</span><span class="sxs-lookup"><span data-stu-id="58a07-105">At run time the connection manager is resolved as a physical ODBC connection.</span></span>  
  
 <span data-ttu-id="58a07-106">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `ODBC`.</span><span class="sxs-lookup"><span data-stu-id="58a07-106">The `ConnectionManagerType` property of the connection manager is set to `ODBC`.</span></span>  
  
 <span data-ttu-id="58a07-107">Puede configurar el administrador de conexiones ODBC de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="58a07-107">You can configure the ODBC connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="58a07-108">Proporcionar una cadena de conexión que haga referencia a un nombre del origen de datos de sistema o usuario.</span><span class="sxs-lookup"><span data-stu-id="58a07-108">Provide a connection string that references a user or system data source name.</span></span>  
  
-   <span data-ttu-id="58a07-109">Especificar el servidor al que debe conectarse.</span><span class="sxs-lookup"><span data-stu-id="58a07-109">Specify the server to connect to.</span></span>  
  
-   <span data-ttu-id="58a07-110">Indicar si la conexión se conserva en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="58a07-110">Indicate whether the connection is retained at run time.</span></span>  
  
## <a name="configuration-of-the-odbc-connection-manager"></a><span data-ttu-id="58a07-111">Configuración del administrador de conexiones ODBC</span><span class="sxs-lookup"><span data-stu-id="58a07-111">Configuration of the ODBC Connection Manager</span></span>  
 <span data-ttu-id="58a07-112">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="58a07-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="58a07-113">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="58a07-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="58a07-114">Referencia de la interfaz de usuario del administrador de conexiones ODBC</span><span class="sxs-lookup"><span data-stu-id="58a07-114">ODBC Connection Manager UI Reference</span></span>](../odbc-connection-manager-ui-reference.md)  
  
 <span data-ttu-id="58a07-115">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="58a07-115">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a07-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58a07-116">See Also</span></span>  
 [<span data-ttu-id="58a07-117">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="58a07-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
