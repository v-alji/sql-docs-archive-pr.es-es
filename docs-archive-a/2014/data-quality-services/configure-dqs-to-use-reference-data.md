---
title: Configurar DQS para usar datos de referencia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.rds.f1
- sql12.dqs.administration.rdsconfiguration.f1
- sql12.dqs.administration.configuration.createDirectRDS.f1
ms.assetid: fae745e7-57a7-4cbc-8979-56ea8e392e4e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 670e984c2afabb70dece75d94701d7a3a03c95bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744324"
---
# <a name="configure-dqs-to-use-reference-data"></a><span data-ttu-id="7deee-102">Configurar DQS para utilizar datos de referencia</span><span class="sxs-lookup"><span data-stu-id="7deee-102">Configure DQS to Use Reference Data</span></span>
  <span data-ttu-id="7deee-103">En este tema se describe cómo configurar [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) con el fin de utilizar datos de referencia para limpiar los datos.</span><span class="sxs-lookup"><span data-stu-id="7deee-103">This topic describes how to configure [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) to use reference data for cleansing your data.</span></span> <span data-ttu-id="7deee-104">Puede usar datos de referencia de Azure Marketplace o de proveedores directos de datos de referencia de terceros en línea.</span><span class="sxs-lookup"><span data-stu-id="7deee-104">You could either use reference data from Azure Marketplace or from direct online third-party reference data providers.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="7deee-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="7deee-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7deee-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7deee-106">Prerequisites</span></span>  
 <span data-ttu-id="7deee-107">Para utilizar datos de referencia de Marketplace, es necesario tener una clave de cuenta de Marketplace válida.</span><span class="sxs-lookup"><span data-stu-id="7deee-107">To use reference data from Marketplace, you must have a valid Marketplace account key.</span></span> <span data-ttu-id="7deee-108">Para obtener información detallada sobre cómo crear una clave de cuenta de Marketplace, vea [crear su cuenta](https://go.microsoft.com/fwlink/?LinkId=212936) ( https://go.microsoft.com/fwlink/?LinkId=212936) .</span><span class="sxs-lookup"><span data-stu-id="7deee-108">For detailed information about creating a Marketplace account key, see [Create Your Account](https://go.microsoft.com/fwlink/?LinkId=212936) (https://go.microsoft.com/fwlink/?LinkId=212936).</span></span> <span data-ttu-id="7deee-109">También es posible crear una clave de cuenta de Marketplace desde [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] ; para ello, haga clic en **Configuración** en el área **Administración** de la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] y, a continuación, haga clic en **Crear un id. de cuenta de DataMarket** en la pestaña **Datos de referencia** .</span><span class="sxs-lookup"><span data-stu-id="7deee-109">You can also create a Marketplace account key from within [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] by clicking **Configuration** under **Administration** in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, and then clicking **Create a DataMarket Account ID** under the **Reference Data** tab.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7deee-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7deee-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7deee-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="7deee-111">Permissions</span></span>  
 <span data-ttu-id="7deee-112">Para configurar servicios de datos de referencia en DQS, debe disponer del rol dqs_administrator en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="7deee-112">You must have the dqs_administrator role on the DQS_MAIN database to configure reference data service settings in DQS.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-marketplace"></a><a name="Marketplace"></a> <span data-ttu-id="7deee-113">Configurar DQS para utilizar datos de referencia de Marketplace</span><span class="sxs-lookup"><span data-stu-id="7deee-113">Configure DQS to Use Reference Data from Marketplace</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="7deee-114">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="7deee-114">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="7deee-115">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , en **Administración**, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="7deee-115">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="7deee-116">En la pestaña **Datos de referencia** , en el área **Configuración de red** , escriba los valores apropiados en los cuadros **Servidor proxy** y **Puerto** si utiliza un servidor proxy para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="7deee-116">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="7deee-117">Especifique la clave de cuenta de Marketplace en el cuadro **Id. de cuenta de DataMarket** y haga clic en el icono **Validar el id. de cuenta de DataMarket** para validarla.</span><span class="sxs-lookup"><span data-stu-id="7deee-117">Specify the Marketplace account key in the **DataMarket Account ID** box, and click the **Validate DataMarket Account ID** icon to validate the account key.</span></span> <span data-ttu-id="7deee-118">Aparecerá un mensaje que indicará si la clave de cuenta de Marketplace especificada es válida.</span><span class="sxs-lookup"><span data-stu-id="7deee-118">A message appears to display whether the specified Marketplace account key is valid.</span></span>  
  
 <span data-ttu-id="7deee-119">Ahora ya está preparado para utilizar en DQS los servicios de datos de referencia de Marketplace a los que está suscrita la clave de cuenta de Marketplace especificada.</span><span class="sxs-lookup"><span data-stu-id="7deee-119">You are now ready to use the reference data services from Marketplace in DQS that are subscribed for the specified Marketplace account key.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-direct-online-third-party-reference-data-providers"></a><a name="ThirdParty"></a> <span data-ttu-id="7deee-120">Configurar DQS para utilizar datos de referencia de proveedores directos de datos de referencia de terceros en línea</span><span class="sxs-lookup"><span data-stu-id="7deee-120">Configure DQS to Use Reference Data from Direct Online Third-Party Reference Data Providers</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="7deee-121">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="7deee-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="7deee-122">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , en **Administración**, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="7deee-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="7deee-123">En la pestaña **Datos de referencia** , en el área **Configuración de red** , escriba los valores apropiados en los cuadros **Servidor proxy** y **Puerto** si utiliza un servidor proxy para conectarse a Internet.</span><span class="sxs-lookup"><span data-stu-id="7deee-123">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="7deee-124">En el área **Configuración del servicio directo de datos de referencia de terceros en línea** , haga clic en el icono **Agregar un nuevo proveedor de servicios de datos de referencia** .</span><span class="sxs-lookup"><span data-stu-id="7deee-124">In the **Direct Online 3rd Party Reference Data Service Settings** area, click the **Add new reference data service provider** icon.</span></span>  
  
5.  <span data-ttu-id="7deee-125">En el cuadro de diálogo **Crear un nuevo proveedor de servicios directos de datos de referencia de terceros en línea** , especifique los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="7deee-125">In the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box, specify the following details:</span></span>  
  
    1.  <span data-ttu-id="7deee-126">En el cuadro **Nombre** , escriba el nombre del nuevo proveedor de servicios directos de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7deee-126">In the **Name** box, type a name of the new direct reference data service provider.</span></span>  
  
    2.  <span data-ttu-id="7deee-127">(Opcional) en el cuadro **Descripción** , escriba una descripción para el nuevo proveedor de servicios directos de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7deee-127">(Optional) In the **Description** box, type a description of the new direct reference data service provider.</span></span>  
  
    3.  <span data-ttu-id="7deee-128">En el cuadro **Categoría** , escriba la categoría de los datos proporcionados por el nuevo proveedor de servicios directos de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7deee-128">In the **Category** box, type the category of the data provided by the new direct reference data service provider.</span></span>  
  
    4.  <span data-ttu-id="7deee-129">En el cuadro Esquema, especifique el esquema que define la cadena de los campos (nombres de columna) que se van a utilizar del proveedor de servicios directos de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7deee-129">In the Schema box, specify the schema that defines the string of fields (column names) to be used from the direct reference data service provider.</span></span> <span data-ttu-id="7deee-130">Los nombres de campo no pueden incluir espacios, y los campos deben ir separados con comas.</span><span class="sxs-lookup"><span data-stu-id="7deee-130">A field name should not contain a space, and the fields should be separated by commas.</span></span> <span data-ttu-id="7deee-131">Por ejemplo: `FirstName, LastName, City, State`.</span><span class="sxs-lookup"><span data-stu-id="7deee-131">For example: `FirstName, LastName, City, State`.</span></span>  
  
    5.  <span data-ttu-id="7deee-132">En el cuadro **URI** , escriba el URI del proveedor de servicios directos de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7deee-132">In the **URI** box, type the URI of the direct reference data service provider.</span></span> <span data-ttu-id="7deee-133">Solo se permiten URI seguros (aquellos cuya dirección empieza por "https://") en DQS.</span><span class="sxs-lookup"><span data-stu-id="7deee-133">Only secure URIs (address starting with "https://") are allowed in DQS.</span></span>  
  
    6.  <span data-ttu-id="7deee-134">En el cuadro **Tamaño máximo de lote**, escriba el número máximo de registros por lote que se enviarán al proveedor de servicios de datos de referencia para la limpieza.</span><span class="sxs-lookup"><span data-stu-id="7deee-134">In the **Max Batch Size** box, type the maximum number of records per batch that will be sent to the reference data service provider for cleansing.</span></span> <span data-ttu-id="7deee-135">Se puede especificar un máximo de 100 registros por lote para la actividad de limpieza.</span><span class="sxs-lookup"><span data-stu-id="7deee-135">A maximum of 100 records per batch can be specified for the cleansing activity.</span></span>  
  
    7.  <span data-ttu-id="7deee-136">En el cuadro **Id. de cuenta** , escriba el identificador de cuenta del suscriptor al proveedor de servicios de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7deee-136">In the **Account ID** box, type the account ID of the subscriber with the reference data service provider.</span></span>  
  
6.  <span data-ttu-id="7deee-137">Haga clic en **Aceptar** para guardar los datos y cerrar el cuadro de diálogo **Crear un nuevo proveedor de servicios directos de datos de referencia de terceros en línea** .</span><span class="sxs-lookup"><span data-stu-id="7deee-137">Click **OK** to save the data, and close the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box.</span></span> <span data-ttu-id="7deee-138">El proveedor directo de datos de referencia de terceros en línea recién agregado estará disponible en la cuadrícula **Proveedores de servicios directos de datos de referencia** en DQS.</span><span class="sxs-lookup"><span data-stu-id="7deee-138">The newly added direct online third party reference data provider becomes available in the **Direct Reference Data Service Providers Grid** in DQS.</span></span>  
  
 <span data-ttu-id="7deee-139">Ahora ya puede utilizar los servicios de datos de referencia del proveedor de servicios directos de datos de referencia de terceros en línea que se acaba de configurar en DQS.</span><span class="sxs-lookup"><span data-stu-id="7deee-139">You are now ready to use the reference data services from the newly configured direct online third-party reference data service provider in DQS.</span></span>  
  
##  <a name="follow-up-after-configuring-dqs-to-use-reference-data"></a><a name="FollowUp"></a><span data-ttu-id="7deee-140">Seguimiento: después de configurar DQS para usar datos de referencia</span><span class="sxs-lookup"><span data-stu-id="7deee-140">Follow Up: After Configuring DQS to use Reference Data</span></span>  
 <span data-ttu-id="7deee-141">A continuación, debe asignar los dominios de la base de conocimiento necesarios a los datos de referencia disponibles en los proveedores de datos que acaba de configurar.</span><span class="sxs-lookup"><span data-stu-id="7deee-141">You must now map the required knowledge base domains to the reference data available from the data providers you just configured.</span></span> <span data-ttu-id="7deee-142">Para ello, vea [adjuntar un dominio o un dominio compuesto a datos de referencia](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="7deee-142">To do so, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
  
