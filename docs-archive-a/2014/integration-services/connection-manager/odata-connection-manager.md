---
title: Administrador de conexiones OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674261"
---
# <a name="odata-connection-manager"></a><span data-ttu-id="bb782-102">Administrador de conexiones OData</span><span class="sxs-lookup"><span data-stu-id="bb782-102">OData Connection Manager</span></span>
  <span data-ttu-id="bb782-103">Un administrador de conexiones OData permite que un paquete se conecte a un origen OData.</span><span class="sxs-lookup"><span data-stu-id="bb782-103">An OData connection manager enables a package to connect to an OData source.</span></span> <span data-ttu-id="bb782-104">Un componente de origen OData se conecta a un origen OData mediante un administrador de conexiones OData y usa datos del servicio.</span><span class="sxs-lookup"><span data-stu-id="bb782-104">An OData Source component connects to an OData source using an OData connection manager and consumes data from the service.</span></span> <span data-ttu-id="bb782-105">Vea la sección [OData Source](../data-flow/odata-source.md)para obtener información detallada, incluidas las instrucciones de instalación de estos componentes.</span><span class="sxs-lookup"><span data-stu-id="bb782-105">See [OData Source](../data-flow/odata-source.md)section for detailed information including the installation instructions for these components.</span></span>  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a><span data-ttu-id="bb782-106">Agregar un administrador de conexiones a un paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="bb782-106">Adding Connection Manager to an SSIS Package</span></span>  
 <span data-ttu-id="bb782-107">Hay tres formas de agregar un nuevo administrador de conexiones OData a un paquete SSIS:</span><span class="sxs-lookup"><span data-stu-id="bb782-107">You can add a new OData Connection Manager to an SSIS package in three ways:</span></span>  
  
-   <span data-ttu-id="bb782-108">Haga clic en el botón **Nuevo…** en el **Editor de origen de OData**.</span><span class="sxs-lookup"><span data-stu-id="bb782-108">Click the **New...** button in the **OData Source Editor**</span></span>  
  
-   <span data-ttu-id="bb782-109">Haga clic con el botón secundario en la carpeta **Administradores de conexiones** en el **Explorador de soluciones** y, a continuación, haga clic en **Nuevo administrador de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="bb782-109">Right-click **Connection Managers** folder in the **Solution Explorer** and click **New Connection Manager**.</span></span> <span data-ttu-id="bb782-110">Seleccione **ODATA** en **Tipo de administrador de conexión**.</span><span class="sxs-lookup"><span data-stu-id="bb782-110">Select **ODATA** for **Connection manager type**.</span></span>  
  
-   <span data-ttu-id="bb782-111">Haga clic con el botón derecho en el panel **administradores de conexiones** en la parte inferior del diseñador de paquetes y seleccione **nueva conexión..**.. Seleccione **ODATA** en **tipo de administrador de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="bb782-111">Right-click in the **Connection Managers** pane at the bottom of the package designer, and select **New Connection...**. Select **ODATA** for **Connection manager type**.</span></span>  
  
## <a name="connection-manager-authentication"></a><span data-ttu-id="bb782-112">Autenticación del administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="bb782-112">Connection Manager Authentication</span></span>  
 <span data-ttu-id="bb782-113">El administrador de conexiones OData admite dos modos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="bb782-113">The OData Connection Manager supports two modes of authentication.</span></span>  
  
-   <span data-ttu-id="bb782-114">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="bb782-114">Windows Authentication</span></span>  
  
-   <span data-ttu-id="bb782-115">Autenticación básica (nombre de usuario y contraseña)</span><span class="sxs-lookup"><span data-stu-id="bb782-115">Basic Authentication (username/password)</span></span>  
  
 <span data-ttu-id="bb782-116">Para el acceso anónimo, seleccione la opción Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="bb782-116">For anonymous access, select the Windows Authentication option</span></span>  
  
### <a name="specifying-and-securing-credentials"></a><span data-ttu-id="bb782-117">Especificar y proteger las credenciales</span><span class="sxs-lookup"><span data-stu-id="bb782-117">Specifying and Securing Credentials</span></span>  
 <span data-ttu-id="bb782-118">Si el servicio OData requiere autenticación básica, puede especificar un nombre de usuario y una contraseña en el [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="bb782-118">If your OData service requires basic authentication, you can specify a username and password in the [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span></span> <span data-ttu-id="bb782-119">Los valores que especifica en el editor se conservan en el paquete.</span><span class="sxs-lookup"><span data-stu-id="bb782-119">The values you enter in the editor are persisted in the package.</span></span> <span data-ttu-id="bb782-120">El valor de contraseña se cifra según el nivel de protección del paquete.</span><span class="sxs-lookup"><span data-stu-id="bb782-120">The password value is encrypted according to the package protection level.</span></span>  
  
 <span data-ttu-id="bb782-121">Hay varias maneras de externalizar/parametrizar los valores de nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="bb782-121">There are multiple ways to externalize/parameterize the username and password values.</span></span> <span data-ttu-id="bb782-122">Las dos métodos principales de hacerlo en [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] son mediante parámetros o estableciendo las propiedades del administrador de conexiones directamente al ejecutar el paquete con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="bb782-122">The two primary ways of doing this in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] are by using parameters, or by setting the connection manager properties directly when you run the package using SQL Server Management Studio.</span></span>  
  
## <a name="odata-connection-manager-properties"></a><span data-ttu-id="bb782-123">Propiedades del administrador de conexiones OData</span><span class="sxs-lookup"><span data-stu-id="bb782-123">OData Connection Manager Properties</span></span>  
 <span data-ttu-id="bb782-124">En la lista siguiente se describen algunas de las propiedades del administrador de conexiones OData que quizás desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="bb782-124">The following list describes some of the OData Connection Manager properties that you may want to change.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb782-125">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bb782-125">Property</span></span>|<span data-ttu-id="bb782-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb782-126">Description</span></span>|  
|<span data-ttu-id="bb782-127">Url</span><span class="sxs-lookup"><span data-stu-id="bb782-127">Url</span></span>|<span data-ttu-id="bb782-128">Dirección URL al documento de servicio.</span><span class="sxs-lookup"><span data-stu-id="bb782-128">URL to the service document.</span></span>|  
|<span data-ttu-id="bb782-129">UserName</span><span class="sxs-lookup"><span data-stu-id="bb782-129">UserName</span></span>|<span data-ttu-id="bb782-130">Nombre de usuario que se va a usar para la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="bb782-130">Username to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="bb782-131">Contraseña</span><span class="sxs-lookup"><span data-stu-id="bb782-131">Password</span></span>|<span data-ttu-id="bb782-132">Contraseña que se va a usar para la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="bb782-132">Password to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="bb782-133">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="bb782-133">ConnectionString</span></span>|<span data-ttu-id="bb782-134">Refleja otras propiedades del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="bb782-134">Reflects other properties of the connection manager.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb782-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb782-135">See Also</span></span>  
 [<span data-ttu-id="bb782-136">Editor del administrador de conexiones OData</span><span class="sxs-lookup"><span data-stu-id="bb782-136">OData Connection Manager Editor</span></span>](../odata-connection-manager-editor.md)  
  
  
