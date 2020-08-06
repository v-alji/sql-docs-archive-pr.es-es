---
title: Introducción a las extensiones de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], about extensions
ms.assetid: 1d652605-9313-4c75-98b4-ba4dcbbb222d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e589d3a4e090aee52d2590c0b2ccff435c2321a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671937"
---
# <a name="data-processing-extensions-overview"></a><span data-ttu-id="16750-102">Introducción a las extensiones de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="16750-102">Data Processing Extensions Overview</span></span>
  <span data-ttu-id="16750-103">Las extensiones de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permiten conectarse a los orígenes de datos y recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="16750-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="16750-104">También actúan como puente entre un origen de datos y un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="16750-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="16750-105">Las extensiones de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] se modelan según un subconjunto de las interfaces del proveedor de datos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16750-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>

 <span data-ttu-id="16750-106">En la tabla siguiente se enumeran las extensiones de procesamiento de datos incluidas con [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16750-106">The following table lists the data processing extensions included with [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

|<span data-ttu-id="16750-107">Extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="16750-107">Data processing extension</span></span>|<span data-ttu-id="16750-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="16750-108">Description</span></span>|
|-------------------------------|-----------------|
|<span data-ttu-id="16750-109">Extensión de procesamiento de datos para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16750-109">Data processing extension for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="16750-110">Usa el Proveedor de datos de .NET Framework para SQL Server con el fin de conectarse a [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] y recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="16750-110">Uses the .NET Framework Data Provider for SQL Server to connect to and retrieve data from the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)].</span></span>|
|<span data-ttu-id="16750-111">Extensión de procesamiento de datos para OLE DB</span><span class="sxs-lookup"><span data-stu-id="16750-111">Data processing extension for OLE DB</span></span>|<span data-ttu-id="16750-112">Usa el Proveedor de datos de .NET Framework para OLE DB.</span><span class="sxs-lookup"><span data-stu-id="16750-112">Uses the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="16750-113">Con esta extensión, el servidor de informes puede consultar cualquier origen de datos que tenga un proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="16750-113">With this extension, the report server can query any data source that has an OLE DB provider.</span></span>|
|<span data-ttu-id="16750-114">Extensión de procesamiento de datos para Oracle</span><span class="sxs-lookup"><span data-stu-id="16750-114">Data processing extension for Oracle</span></span>|<span data-ttu-id="16750-115">Usa el Proveedor de datos de .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="16750-115">Uses the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="16750-116">Con esta extensión, el servidor de informes puede tener acceso a los orígenes de datos de Oracle a través del software de conectividad de cliente de Oracle.</span><span class="sxs-lookup"><span data-stu-id="16750-116">With this extension, the report server can access Oracle data sources through Oracle client connectivity software.</span></span>|
|<span data-ttu-id="16750-117">Extensión de procesamiento de datos para ODBC</span><span class="sxs-lookup"><span data-stu-id="16750-117">Data processing extension for ODBC</span></span>|<span data-ttu-id="16750-118">Usa el Proveedor de datos de .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="16750-118">Uses the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="16750-119">Con esta extensión, el servidor de informes puede tener acceso a los datos de cualquier base de datos para la que haya un controlador ODBC.</span><span class="sxs-lookup"><span data-stu-id="16750-119">With this extension, the report server can access data in any database for which there is an ODBC driver.</span></span>|

 <span data-ttu-id="16750-120">Puede utilizar la API de procesamiento de datos de [!INCLUDE[ssRS](../../../includes/ssrs.md)] para agregar un procesamiento de datos personalizado al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="16750-120">You can use the [!INCLUDE[ssRS](../../../includes/ssrs.md)] data processing API to add custom data processing to your report server.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="16750-121">tiene compatibilidad integrada con los proveedores de datos en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16750-121">has built-in support for data providers in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="16750-122">Si ya ha implementado un proveedor de datos completo, no necesita implementar una extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16750-122">If you have already implemented a full data provider, you do not need to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension.</span></span> <span data-ttu-id="16750-123">Sin embargo, debería considerar extender el proveedor de datos para que incluya la funcionalidad concreta para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 2005, que incluye las credenciales de conexión seguras y los agregados del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="16750-123">However, you should consider extending your data provider to include functionality specific to [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 2005, which includes secure connection credentials and server-side aggregates.</span></span>

 <span data-ttu-id="16750-124">Cada una de las extensiones de procesamiento de datos incluidas con [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa un conjunto común de interfaces.</span><span class="sxs-lookup"><span data-stu-id="16750-124">Each of the data processing extensions included with [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a common set of interfaces.</span></span> <span data-ttu-id="16750-125">De esta forma se asegura de que cada extensión implementa una funcionalidad comparable.</span><span class="sxs-lookup"><span data-stu-id="16750-125">This ensures that each extension implements comparable functionality.</span></span>

 <span data-ttu-id="16750-126">Puede desarrollar extensiones de procesamiento de datos para sus propios orígenes de datos o puede utilizar las interfaces con el fin de agregar un nivel adicional de procesamiento de datos a las infraestructuras de base de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="16750-126">You can develop data processing extensions for your own data sources, or you can use the interfaces to add an additional layer of data processing to common database infrastructures.</span></span> <span data-ttu-id="16750-127">Puede implementar extensiones de procesamiento de datos personalizadas para habilitar la integración sin problemas de los datos en los servidores de informes existentes en una organización.</span><span class="sxs-lookup"><span data-stu-id="16750-127">You can deploy your custom data processing extensions to enable seamless integration of data into the existing report servers in your organization.</span></span> <span data-ttu-id="16750-128">También puede utilizarlas como parte de un conjunto de informes de errores personalizado que se proporciona a los consumidores.</span><span class="sxs-lookup"><span data-stu-id="16750-128">You can also use them as part of a custom reporting suite that you provide to your consumers.</span></span>

 <span data-ttu-id="16750-129">![Arquitectura de extensión de procesamiento de datos](../../media/bk-dataprocess-extensions.gif "Arquitectura de extensiones de procesamiento de datos") Arquitectura de la extensión de procesamiento de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="16750-129">![Data processing extension architecture](../../media/bk-dataprocess-extensions.gif "Data processing extension architecture") Reporting Services data processing extension architecture</span></span>

 <span data-ttu-id="16750-130">Entre las ventajas de implementar una extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] personalizada se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="16750-130">The advantages to implementing a custom [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension include:</span></span>

-   <span data-ttu-id="16750-131">Una arquitectura de acceso a datos simplificada, a menudo con un mejor mantenimiento y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="16750-131">A simplified data access architecture, often with better maintainability and improved performance.</span></span>

-   <span data-ttu-id="16750-132">La capacidad de exponer directamente la funcionalidad específica de la extensión a los consumidores.</span><span class="sxs-lookup"><span data-stu-id="16750-132">The ability to directly expose extension-specific functionality to consumers.</span></span>

-   <span data-ttu-id="16750-133">Una interfaz concreta para los consumidores que permite tener acceso al origen de datos dentro de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16750-133">A specific interface for your consumers to access your data source within [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="data-extension-process-flow"></a><span data-ttu-id="16750-134">Flujo del proceso de la extensión de datos</span><span class="sxs-lookup"><span data-stu-id="16750-134">Data Extension Process Flow</span></span>
 <span data-ttu-id="16750-135">Antes de desarrollar la extensión de datos personalizada, debería entender cómo usa el servidor de informes las extensiones de datos para procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="16750-135">Before developing your custom data extension, you should understand how the report server uses data extensions to process data.</span></span> <span data-ttu-id="16750-136">También debería saber los constructores y los métodos a los que el servidor de informes llama.</span><span class="sxs-lookup"><span data-stu-id="16750-136">You should also understand the constructors and methods that are called by the report server.</span></span>

 <span data-ttu-id="16750-137">![Flujo de proceso para la extensión de procesamiento de datos](../../media/bk-ext-01.gif "Flujo del proceso para extensiones de procesamiento de datos") El flujo de proceso paso a paso de una extensión de datos a la que llama el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="16750-137">![Process flow for data processing extension](../../media/bk-ext-01.gif "Process flow for data processing extension") The step-by-step process flow of a data extension that is called by the report server</span></span>

 <span data-ttu-id="16750-138">En esta ilustración se muestra el siguiente flujo de eventos:</span><span class="sxs-lookup"><span data-stu-id="16750-138">The illustration shows the following sequence of events:</span></span>

1.  <span data-ttu-id="16750-139">El servidor de informes crea un objeto de conexión y lo pasa en la cadena de conexión y en las credenciales asociadas al informe.</span><span class="sxs-lookup"><span data-stu-id="16750-139">The report server creates a connection object and passes in the connection string and credentials associated with the report.</span></span>

2.  <span data-ttu-id="16750-140">El texto de comando del informe se utiliza para crear un objeto de comando.</span><span class="sxs-lookup"><span data-stu-id="16750-140">The command text of the report is used to create a command object.</span></span> <span data-ttu-id="16750-141">En el proceso, la extensión de procesamiento de datos puede incluir código que analiza el texto del comando y crea los parámetros para el comando.</span><span class="sxs-lookup"><span data-stu-id="16750-141">In the process, the data processing extension may include code that parses the command text and creates any parameters for the command.</span></span>

3.  <span data-ttu-id="16750-142">Una vez procesados el objeto de comando y cualquier parámetro, se genera un lector de datos que devuelve un conjunto de resultados y permite al servidor de informes asociar los datos del informe al diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="16750-142">Once the command object and any parameters are processed, a data reader is generated that returns a result set and enables the report server to associate the report data with the report layout.</span></span>

## <a name="developer-requirements"></a><span data-ttu-id="16750-143">Requisitos para el programador</span><span class="sxs-lookup"><span data-stu-id="16750-143">Developer Requirements</span></span>
 <span data-ttu-id="16750-144">Al desarrollar una extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], es necesario tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16750-144">Developing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension requires you to have:</span></span>

-   <span data-ttu-id="16750-145">Un equipo de implementación con el Diseñador de informes o un servidor de informes instalado.</span><span class="sxs-lookup"><span data-stu-id="16750-145">A deployment computer with Report Designer or a report server installed.</span></span>

-   <span data-ttu-id="16750-146">Un equipo de desarrollo con [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] o superior, o el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Kit de desarrollo de software (SDK) de instalado.</span><span class="sxs-lookup"><span data-stu-id="16750-146">A development computer with [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] or above, or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Software Development Kit (SDK) installed.</span></span>

-   <span data-ttu-id="16750-147">Una comprensión detallada de las características y capacidades de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16750-147">An in-depth understanding of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] features and capabilities.</span></span>

-   <span data-ttu-id="16750-148">Una comprensión detallada de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] la arquitectura, [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] los proveedores de datos, los objetos de conjunto de datos ADO.net y las [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] interfaces comunes.</span><span class="sxs-lookup"><span data-stu-id="16750-148">An in-depth understanding of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] architecture, [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data providers, ADO.NET DataSet objects, and the common [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] interfaces.</span></span>

-   <span data-ttu-id="16750-149">Experiencia de desarrollo en un [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] lenguaje como [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .net.</span><span class="sxs-lookup"><span data-stu-id="16750-149">Development experience in a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] language such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="16750-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16750-150">See Also</span></span>
 <span data-ttu-id="16750-151">[Reporting Services biblioteca](../reporting-services-extension-library.md) de [extensiones de Reporting Services Extensions](../reporting-services-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="16750-151">[Reporting Services Extensions](../reporting-services-extensions.md) [Reporting Services Extension Library](../reporting-services-extension-library.md)</span></span>

