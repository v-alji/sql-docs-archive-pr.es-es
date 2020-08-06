---
title: Servicios de datos de referencia en DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ef217717-6d05-443e-af26-44dc745a349d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4ed286b5834d81f775ee097672bfbc861c0b369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673283"
---
# <a name="reference-data-services-in-dqs"></a><span data-ttu-id="dd0db-102">Servicios de datos de referencia en DQS</span><span class="sxs-lookup"><span data-stu-id="dd0db-102">Reference Data Services in DQS</span></span>
  <span data-ttu-id="dd0db-103">Los datos de referencia hacen referencia a un conjunto completo y preciso de datos globales relacionados o clasificados (más allá de los límites de una empresa) que está disponible en dominios públicos de confianza o en proveedores de contenido comercial premium.</span><span class="sxs-lookup"><span data-stu-id="dd0db-103">Reference data refers to an accurate and complete set of related or categorized global data (beyond the boundaries of an enterprise) that is available at trusted public domains or from premium commercial content providers.</span></span>  
  
 <span data-ttu-id="dd0db-104">La característica Reference Data Service de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) le permite suscribirse a proveedores de datos de referencia de terceros, y limpiar y enriquecer fácilmente sus datos empresariales validándolos con los datos de alta calidad de dichos proveedores.</span><span class="sxs-lookup"><span data-stu-id="dd0db-104">The Reference Data Service feature in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) enables you to subscribe to third-party reference data providers, and to easily cleanse and enrich your business data by validating it against their high-quality data.</span></span> <span data-ttu-id="dd0db-105">Puede utilizar servicios de proveedores de servicios de calidad de datos punteros desde DQS para normalizar, corregir o enriquecer los datos durante el proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="dd0db-105">You can use services from leading data quality service providers from within DQS to standardize, correct, or enrich your data during the cleansing process.</span></span> <span data-ttu-id="dd0db-106">Por ejemplo, puede comparar una lista de prefijos telefónicos o de códigos postales con los datos de referencia para validar las direcciones de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="dd0db-106">For example, you can use a list of area codes or zip codes against the reference data to validate addresses of your customers.</span></span>  
  
 <span data-ttu-id="dd0db-107">La característica Reference Data Service ofrece las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd0db-107">The Reference Data Service feature has the following benefits:</span></span>  
  
-   <span data-ttu-id="dd0db-108">Los datos de referencia le permiten garantizar la calidad de los datos comparándoles con los datos garantizados por una empresa de terceros.</span><span class="sxs-lookup"><span data-stu-id="dd0db-108">Reference data enables you to ensure the quality of your data by comparing it to data guaranteed by a third-party company.</span></span>  
  
-   <span data-ttu-id="dd0db-109">El proceso de datos de referencia se incorpora en la generación de bases de conocimiento de DQS y en los proyectos de calidad de datos, lo que le permite establecer un proceso de calidad de datos completo.</span><span class="sxs-lookup"><span data-stu-id="dd0db-109">The reference data process is incorporated into DQS knowledge base building and a data quality project, enabling you to institute a comprehensive data quality process.</span></span>  
  
-   <span data-ttu-id="dd0db-110">Admite el uso de datos de referencia de Azure Marketplace, así como directamente de proveedores de datos de referencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="dd0db-110">Supports using reference data from Azure Marketplace as well as directly from third party reference data providers.</span></span>  
  
##  <a name="using-reference-data-from-azure-marketplace"></a><a name="Marketplace"></a><span data-ttu-id="dd0db-111">Uso de datos de referencia de Azure Marketplace</span><span class="sxs-lookup"><span data-stu-id="dd0db-111">Using Reference Data from Azure Marketplace</span></span>  
 <span data-ttu-id="dd0db-112">DQS admite el uso de datos de referencia de Azure Marketplace para permitir a los proveedores de contenido proporcionar servicios de datos de referencia a través de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dd0db-112">DQS supports using reference data from Azure Marketplace to enable content providers to provide reference data services through Marketplace.</span></span> <span data-ttu-id="dd0db-113">Marketplace es un servicio de Microsoft que proporciona un único canal de catálogo de soluciones y entrega de datos de alta calidad y aplicaciones como servicio basado en nube.</span><span class="sxs-lookup"><span data-stu-id="dd0db-113">Marketplace is a service from Microsoft that provides a single marketplace and delivery channel for high-quality data and applications as cloud services.</span></span> <span data-ttu-id="dd0db-114">Para obtener más información sobre Marketplace, consulte [más información sobre Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/).</span><span class="sxs-lookup"><span data-stu-id="dd0db-114">For more information about Marketplace, see [Learn About Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/).</span></span>  
  
 <span data-ttu-id="dd0db-115">La perfecta integración entre Marketplace y DQS simplifica los pasos asociados con la detección, búsqueda y adquisición de información para los proyectos de calidad de datos desde DQS.</span><span class="sxs-lookup"><span data-stu-id="dd0db-115">The seamless integration between Marketplace and DQS simplifies the steps associated with discovering, exploring, and acquiring information for data quality projects from within DQS.</span></span> <span data-ttu-id="dd0db-116">Los datos se utilizan desde DQS, y los usuarios de DQS pueden conseguir datos de alta calidad aunando las características de DQS, Marketplace y los proveedores de servicios de datos de referencia de una manera innovadora.</span><span class="sxs-lookup"><span data-stu-id="dd0db-116">The data is consumed from DQS, and helps DQS users achieve high data quality by bringing together DQS, Marketplace, and reference data service providers in an innovative way.</span></span>  
  
 <span data-ttu-id="dd0db-117">Para utilizar los datos de referencia de Marketplace en DQS para la actividad de limpieza, es necesario disponer de una clave de cuenta de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dd0db-117">To use reference data from Marketplace in DQS for the cleansing activity, you must have a Marketplace account key.</span></span> <span data-ttu-id="dd0db-118">La creación de una clave de cuenta de Marketplace es gratuita, y solo deberá pagar si se suscribe a conjuntos de datos de pago.</span><span class="sxs-lookup"><span data-stu-id="dd0db-118">Creating a Marketplace account key is free, and you pay only if you subscribe to paid datasets.</span></span> <span data-ttu-id="dd0db-119">La suscripción a conjuntos de datos gratuitos, así como su uso, no supone ningún cargo.</span><span class="sxs-lookup"><span data-stu-id="dd0db-119">There is no charge for subscribing to, and using free datasets.</span></span> <span data-ttu-id="dd0db-120">Para obtener información detallada sobre cómo crear una clave de cuenta de Marketplace, vea [crear su cuenta](https://go.microsoft.com/fwlink/?LinkId=212936) ( https://go.microsoft.com/fwlink/?LinkId=212936) .</span><span class="sxs-lookup"><span data-stu-id="dd0db-120">For detailed information about creating a Marketplace account key, see [Create Your Account](https://go.microsoft.com/fwlink/?LinkId=212936) (https://go.microsoft.com/fwlink/?LinkId=212936).</span></span>  
  
 <span data-ttu-id="dd0db-121">Además, puede realizar las siguientes actividades de Marketplace desde DQS:</span><span class="sxs-lookup"><span data-stu-id="dd0db-121">Additionally, you can perform the following Marketplace activities from within DQS:</span></span>  
  
-   <span data-ttu-id="dd0db-122">Examinar conjuntos de datos en Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dd0db-122">Browse data sets in Marketplace.</span></span>  
  
-   <span data-ttu-id="dd0db-123">Crear una clave de cuenta de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dd0db-123">Create a Marketplace account key.</span></span>  
  
-   <span data-ttu-id="dd0db-124">Administrar los detalles de la cuenta de Marketplace, como las claves de cuenta y las suscripciones a los proveedores de datos.</span><span class="sxs-lookup"><span data-stu-id="dd0db-124">Manage your Marketplace account details such as account keys and subscriptions to data providers.</span></span>  
  
 <span data-ttu-id="dd0db-125">Puede realizar estas actividades en la pestaña **Datos de referencia** de la pantalla **Configuración** de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd0db-125">You can perform these activities in the **Reference Data** tab of the **Configuration** screen in [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
##  <a name="using-reference-data-directly-from-the-third-party-reference-data-providers"></a><a name="Direct"></a> <span data-ttu-id="dd0db-126">Usar datos de referencia directamente de los proveedores de datos de referencia de terceros</span><span class="sxs-lookup"><span data-stu-id="dd0db-126">Using Reference Data Directly from the Third Party Reference Data Providers</span></span>  
 <span data-ttu-id="dd0db-127">Si no está conectado a Internet y no puede usar Marketplace, DQS también admite la conexión directa con los proveedores de datos que estén disponibles en la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="dd0db-127">If you are not connected to the Internet and therefore cannot use Marketplace, DQS also supports direct connection to data providers that are available within your organization's network.</span></span> <span data-ttu-id="dd0db-128">Si desea utilizar datos de referencia de un proveedor directo de datos de referencia de terceros en línea, deberá crear un registro para dicho proveedor en DQS.</span><span class="sxs-lookup"><span data-stu-id="dd0db-128">To use reference data from direct online third-party reference data providers, you have to create a record for the data provider in DQS.</span></span>  
  
##  <a name="how-to-cleanse-data-by-using-the-reference-data"></a><a name="HowToCleanse"></a> <span data-ttu-id="dd0db-129">Cómo limpiar datos mediante el uso de datos de referencia</span><span class="sxs-lookup"><span data-stu-id="dd0db-129">How to Cleanse Data by Using the Reference Data</span></span>  
 <span data-ttu-id="dd0db-130">La limpieza de los datos en DQS mediante los datos de referencia incluye los tres pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd0db-130">Cleansing your data in DQS using reference data includes the following three steps:</span></span>  
  
1.  <span data-ttu-id="dd0db-131">**Configurar los detalles del proveedor de datos de referencia en DQS**: si desea usar datos de referencia en DQS, deberá configurar en este los detalles del servicio de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="dd0db-131">**Configuring the reference data provider details in DQS**: Before you can use reference data in DQS, you must configure reference data service details in DQS.</span></span>  
  
    1.  <span data-ttu-id="dd0db-132">Si utiliza Marketplace, proporcione una clave de cuenta de Marketplace válida, busque la categoría de datos [Data Quality Services](../data-quality-services/data-quality-services.md) en Marketplace y suscríbase a los proveedores deseados.</span><span class="sxs-lookup"><span data-stu-id="dd0db-132">If you are using Marketplace, provide a valid Marketplace account key, browse to the [Data Quality Services](../data-quality-services/data-quality-services.md) data category in Marketplace, and subscribe to the required providers.</span></span>  
  
    2.  <span data-ttu-id="dd0db-133">Si utiliza un proveedor directo de datos de referencia de terceros en línea, deberá agregar los detalles de este a DQS para poder utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="dd0db-133">If you are using a direct online reference data provider, you must add direct reference data provider details in DQS before you can use it.</span></span>  
  
     <span data-ttu-id="dd0db-134">La configuración de los detalles del proveedor de datos de referencia en DQS es una actividad que se realiza una sola vez para cada proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="dd0db-134">Configuring the reference data provider details in DQS is one time activity for a particular data provider.</span></span> <span data-ttu-id="dd0db-135">Solo los administradores de DQS pueden configurar los valores de los datos de referencia en DQS.</span><span class="sxs-lookup"><span data-stu-id="dd0db-135">Only DQS administrators can configure reference data settings in DQS.</span></span>  
  
2.  <span data-ttu-id="dd0db-136">**Asignar un dominio o un dominio compuesto de una base de conocimiento al servicio de datos de referencia**: asigne un dominio o un dominio compuesto al servicio de datos de referencia apropiado suscrito/agregado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="dd0db-136">**Map a domain/composite domain in a knowledge base to the reference data service**: Map a domain/composite domain to the appropriate reference data service subscribed/added in step 1.</span></span>  
  
3.  <span data-ttu-id="dd0db-137">**Utilizar los dominios asignados para la actividad de limpieza en un proyecto de calidad de datos**: al crear un proyecto de calidad de datos para la actividad **Limpieza** , seleccione la base de conocimiento que contiene los dominios o dominios compuestos asignados a los servicios de datos de referencia en el paso 2 y realice la actividad de limpieza.</span><span class="sxs-lookup"><span data-stu-id="dd0db-137">**Use the Mapped Domains for the Cleansing activity in a data quality project**: While creating a data quality project for the **Cleansing** activity, select the knowledge base that contains domains/composite domains mapped with reference data services in step 2, and perform the cleansing activity.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="dd0db-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="dd0db-138">Related Tasks</span></span>  
  
|<span data-ttu-id="dd0db-139">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="dd0db-139">Task Description</span></span>|<span data-ttu-id="dd0db-140">Tema</span><span class="sxs-lookup"><span data-stu-id="dd0db-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="dd0db-141">Describe cómo configurar DQS para utilizar los servicios de datos de referencia de Marketplace o de proveedores directos de datos de terceros en línea.</span><span class="sxs-lookup"><span data-stu-id="dd0db-141">Describes how to configure DQS to use reference data services from Marketplace or direct third-party online data providers.</span></span>|[<span data-ttu-id="dd0db-142">Configurar DQS para utilizar datos de referencia</span><span class="sxs-lookup"><span data-stu-id="dd0db-142">Configure DQS to Use Reference Data</span></span>](../../2014/data-quality-services/configure-dqs-to-use-reference-data.md)|  
|<span data-ttu-id="dd0db-143">Describe cómo asignar un dominio o un dominio compuesto de una base de conocimiento a un servicio de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="dd0db-143">Describes how to map a domain/composite domain in a knowledge base to a reference data service.</span></span>|[<span data-ttu-id="dd0db-144">Adjuntar un dominio o un dominio compuesto a datos de referencia</span><span class="sxs-lookup"><span data-stu-id="dd0db-144">Attach a Domain or Composite Domain to Reference Data</span></span>](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md)|  
|<span data-ttu-id="dd0db-145">Describe cómo limpiar los datos mediante el servicio de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="dd0db-145">Describes how to cleanse data using reference data service.</span></span>|[<span data-ttu-id="dd0db-146">Limpiar datos mediante el conocimiento de datos de referencia &#40;externo&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0db-146">Cleanse Data Using Reference Data &#40;External&#41; Knowledge</span></span>](../../2014/data-quality-services/cleanse-data-using-reference-data-external-knowledge.md)|  
  
  