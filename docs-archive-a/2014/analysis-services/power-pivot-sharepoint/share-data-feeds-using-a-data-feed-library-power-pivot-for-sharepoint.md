---
title: Compartir fuentes de distribución de datos mediante una biblioteca de fuentes de distribución de datos (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feeds [Analysis Services with SharePoint]
ms.assetid: 4ec98dec-0cd2-4727-bb79-5bf6f8a865d6
author: minewiskan
ms.author: owend
ms.openlocfilehash: cb24a0ae66cdb0b0623aaa217be778280bdb14ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673307"
---
# <a name="share-data-feeds-using-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="3f094-102">Compartir las fuentes de distribución de datos mediante una biblioteca de fuentes de distribución de datos (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3f094-102">Share Data Feeds Using a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="3f094-103">Una fuente de distribución de datos es un flujo de datos XML que se genera a partir de un servicio o aplicación que expone los datos en el formato en línea de Atom.</span><span class="sxs-lookup"><span data-stu-id="3f094-103">A data feed is an XML data stream that is generated from a service or application that exposes data in the Atom wire format.</span></span> <span data-ttu-id="3f094-104">Se usa cada vez más para transportar los datos entre las aplicaciones y a los visores del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="3f094-104">Increasingly, it is used to transport data between applications and to client-side viewers.</span></span> <span data-ttu-id="3f094-105">En una implementación de PowerPivot para SharePoint, las fuentes de distribución de datos se utilizan para rellenar un [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] origen de datos con datos de una aplicación o servicio que tiene en cuenta Atom.</span><span class="sxs-lookup"><span data-stu-id="3f094-105">In a PowerPivot for SharePoint deployment, data feeds are used to populate a [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data source with data from an Atom-aware application or service.</span></span>  
  
 <span data-ttu-id="3f094-106">Si ya utiliza una combinación de aplicaciones que pueden usar Atom, puede que nunca necesite saber cómo se generan y usan las fuentes porque la transferencia de datos se realiza sin problemas entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3f094-106">If you already use a combination of Atom-aware applications, you might never need to know how feeds are generated and consumed because the data transfer is seamless between the applications.</span></span> <span data-ttu-id="3f094-107">Sin embargo, las organizaciones que utilizan soluciones personalizadas para publicar fuentes Atom a menudo necesitan una manera de hacer que las fuentes estén disponibles para los trabajadores de la información.</span><span class="sxs-lookup"><span data-stu-id="3f094-107">However, organizations that use custom solutions to publish Atom feeds often need a way to make feeds available to information workers.</span></span> <span data-ttu-id="3f094-108">Una forma de conseguirlo es crear y compartir archivos de documento de servicio de datos (.atomsvc) que proporcionan las conexiones a los orígenes en línea que producen las fuentes.</span><span class="sxs-lookup"><span data-stu-id="3f094-108">One way to do that is to create and share data service document (.atomsvc) files that provide connections to the online sources that produce the feeds.</span></span> <span data-ttu-id="3f094-109">Una biblioteca de propósito especial, denominada biblioteca de fuentes de distribución de datos, permite crear y compartir los documentos de servicio de datos en una aplicación web de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f094-109">A special-purpose library, called a data feed library, supports creating and sharing data service documents in a SharePoint web application.</span></span>  
  
 <span data-ttu-id="3f094-110">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="3f094-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="3f094-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3f094-111">Prerequisites</span></span>](#prereq)  
  
 [<span data-ttu-id="3f094-112">Crear un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-112">Create a Data Service Document</span></span>](#createdsdoc)  
  
 [<span data-ttu-id="3f094-113">Proteger un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-113">Secure a Data Service Document</span></span>](#securedsdoc)  
  
 [<span data-ttu-id="3f094-114">Modificar un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-114">Modify a Data Service Document</span></span>](#modifydsdoc)  
  
 [<span data-ttu-id="3f094-115">Paso siguiente: usar un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-115">Next Step: Use a Data Service Document</span></span>](#usedsdoc)  
  
> [!NOTE]  
>  <span data-ttu-id="3f094-116">Aunque las fuentes de distribución de datos se usan para agregar datos web a un origen de datos de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] que se cree en [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], cualquier aplicación cliente que pueda leer una fuente Atom puede procesar un documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-116">Although data feeds are used to add Web data to a [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data source that you create in a [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], any client application that can read an Atom feed can process a data service document.</span></span>  
  
##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="3f094-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3f094-117">Prerequisites</span></span>  
 <span data-ttu-id="3f094-118">Debe tener una implementación de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] PowerPivot para SharePoint que agregue [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] el procesamiento de consultas a una granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f094-118">You must have a deployment of [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] PowerPivot for SharePoint that adds [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] query processing to a SharePoint farm.</span></span> <span data-ttu-id="3f094-119">La compatibilidad con las fuentes de distribución de datos se implementa a través del paquete de soluciones de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f094-119">Data Feed support is deployed through the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] solution package.</span></span>  
  
 <span data-ttu-id="3f094-120">Debe tener una biblioteca de SharePoint que admita el tipo de contenido de documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-120">You must have a SharePoint library that supports the data service document content type.</span></span> <span data-ttu-id="3f094-121">Para este fin se recomienda la biblioteca de fuentes de distribución de datos predeterminada, pero puede agregar manualmente el tipo de contenido a cualquier biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3f094-121">A default Data Feed library is recommended for this purpose, but you can manually add the content type to any library.</span></span> <span data-ttu-id="3f094-122">Para obtener más información, vea [crear o personalizar una biblioteca de fuentes de distribución de datos &#40;PowerPivot para SharePoint&#41;](create-or-customize-a-data-feed-library-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="3f094-122">For more information, see [Create or Customize a Data Feed Library &#40;PowerPivot for SharePoint&#41;](create-or-customize-a-data-feed-library-power-pivot-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="3f094-123">Debe tener un servicio de datos o un origen de datos en línea que proporcione datos tabulares XML en el formato Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="3f094-123">You must have a data service or online data source that provides XML tabular data in the Atom 1.0 format.</span></span>  
  
 <span data-ttu-id="3f094-124">Para crear o administrar un documento de servicio de datos en una biblioteca de SharePoint, debe tener los permisos de contribución en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f094-124">You must have Contribute permissions on a SharePoint site to create or manage a data service document in a SharePoint library.</span></span>  
  
##  <a name="create-a-data-service-document"></a><a name="createdsdoc"></a> <span data-ttu-id="3f094-125">Crear un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-125">Create a Data Service Document</span></span>  
 <span data-ttu-id="3f094-126">Un documento de servicio de datos es una solicitud pendiente para transmitir en secuencias los datos tras la solicitud de un origen de datos en línea o una aplicación que proporcione los datos en un formato de fuente.</span><span class="sxs-lookup"><span data-stu-id="3f094-126">A data service document is a standing request to stream data upon request from an online data source or application that provides data in a feed format.</span></span> <span data-ttu-id="3f094-127">Al crear un documento de servicio de datos, se especifica un puntero a uno o varios servicios de datos direccionables con direcciones URL que proporcionan los datos tabulares XML en el formato sindicado de Atom.</span><span class="sxs-lookup"><span data-stu-id="3f094-127">When you create a data service document, you specify a pointer to one or more URL addressable data services that provide XML tabular in Atom syndicated format.</span></span>  
  
 <span data-ttu-id="3f094-128">En un único documento se pueden especificar varias fuentes de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-128">A single document can specify multiple data feeds.</span></span> <span data-ttu-id="3f094-129">Esto es útil si desea recuperar un conjunto de cargas de datos del mismo servicio, o incluso de servicios diferentes, en una única operación de importación.</span><span class="sxs-lookup"><span data-stu-id="3f094-129">This is useful if you want to retrieve a set of data payloads from the same service, or even from different services, in a single import operation.</span></span>  
  
1.  <span data-ttu-id="3f094-130">En un sitio de SharePoint, abra la biblioteca de fuentes de distribución de datos u otra biblioteca de documentos a la que haya agregado el tipo de contenido del servicio de datos y donde lo haya configurado.</span><span class="sxs-lookup"><span data-stu-id="3f094-130">On a SharePoint site, open the Data Feed library or another document library to which you have added and configured the data service content type.</span></span> <span data-ttu-id="3f094-131">Para encontrar una biblioteca de fuentes de distribución de datos que se creara previamente, haga clic en **Ver todos** en Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="3f094-131">To find a Data Feed library that was previously created, click **View All** on the Quick Launch.</span></span>  
  
2.  <span data-ttu-id="3f094-132">En la cinta de opciones en la parte superior de la página, en Herramientas de documento, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="3f094-132">On the ribbon at the top of the page, in Document Tools, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="3f094-133">Haga clic en **Nuevo documento** y, a continuación, seleccione **Documento de servicio de datos**.</span><span class="sxs-lookup"><span data-stu-id="3f094-133">Click **New Document,** and then select **Data Service Document**.</span></span>  
  
4.  <span data-ttu-id="3f094-134">En la página Nueva documento de servicio de datos, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3f094-134">In the New Data Service Document page, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="3f094-135">El nombre y la descripción del documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-135">A name and description for the data service document.</span></span> <span data-ttu-id="3f094-136">Asegúrese de proporcionar detalles suficientes para que los usuarios puedan determinar si utilizan la fuente.</span><span class="sxs-lookup"><span data-stu-id="3f094-136">Be sure to provide sufficient detail so that users can determine whether to use the feed.</span></span>  
  
    2.  <span data-ttu-id="3f094-137">En Fuente de datos, escriba una dirección URL a un servicio de datos o aplicación web que proporcione los datos en el formato de Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="3f094-137">In Data Feed, enter a URL to a data service or Web application that provides data in the Atom 1.0 format.</span></span>  
  
         <span data-ttu-id="3f094-138">La dirección URL se debe resolver como un servicio que devuelva los datos estructurados o semiestructurados en filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="3f094-138">The URL must resolve to a service that returns structured or semi-structured data in rows and columns.</span></span> <span data-ttu-id="3f094-139">El servicio debería devolver los datos anónimamente o a través de las credenciales de seguridad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="3f094-139">The service should return data anonymously or via the security credentials of the current user.</span></span>  
  
         <span data-ttu-id="3f094-140">La dirección URL se debe resolver como un servicio compatible con la Autenticación de Windows, la autenticación básica o el acceso anónimo.</span><span class="sxs-lookup"><span data-stu-id="3f094-140">The URL must resolve to a service that supports Windows Authentication, Basic authentication, or anonymous access.</span></span> <span data-ttu-id="3f094-141">El usuario que importa la fuente especifica qué esquema utilizar.</span><span class="sxs-lookup"><span data-stu-id="3f094-141">The user who imports the feed specifies which scheme to use.</span></span> <span data-ttu-id="3f094-142">La seguridad integrada está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f094-142">Integrated security is selected by default.</span></span>  
  
         <span data-ttu-id="3f094-143">La dirección URL de una fuente de distribución de datos puede incluir parámetros.</span><span class="sxs-lookup"><span data-stu-id="3f094-143">A data feed URL can include parameters.</span></span> <span data-ttu-id="3f094-144">Diferentes tipos de tecnologías de servicios de datos admiten esquemas de direccionamiento URL avanzados que permiten seleccionar con precisión los datos que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="3f094-144">Different types of data service technologies support advanced URL addressing schemes that allow you to precisely select the data you want to use.</span></span> <span data-ttu-id="3f094-145">Por ejemplo, un servicio de datos de ADO.NET proporciona los parámetros de dirección URL para especificar las entidades, asociaciones y rutas de navegación en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="3f094-145">For example, an ADO.NET data service provides URL parameters for specifying entities, associations, and navigation paths in the underlying data.</span></span> <span data-ttu-id="3f094-146">Al especificar una dirección URL compleja como origen de una fuente de distribución de datos, puede especificar con precisión el conjunto de datos que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="3f094-146">By specifying a complex URL as a source of a data feed, you can precisely specify the dataset you want to use.</span></span>  
  
    3.  <span data-ttu-id="3f094-147">Para la misma fuente de distribución de datos, escriba un nombre de tabla que identifique posteriormente el conjunto de datos en una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="3f094-147">For the same data feed, enter a table name that subsequently identifies the dataset in a client application.</span></span> <span data-ttu-id="3f094-148">En [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], cada fuente de distribución de datos que importe se coloca en su propio control de tabla en un origen de datos de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f094-148">In the [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], each data feed that you import is placed in its own table control in an [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data source.</span></span> <span data-ttu-id="3f094-149">Debe especificar el nombre de la tabla que recibe los datos importados al configurar la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-149">You must specify the name of the table that receives the imported data when you set up the data feed.</span></span>  
  
5.  <span data-ttu-id="3f094-150">Haga clic en "Agregar otra fuente de distribución de datos" para repetir los pasos previos y especificar fuentes adicionales del mismo servicio o de un servicio diferente.</span><span class="sxs-lookup"><span data-stu-id="3f094-150">Click "Add another data feed" to repeat the previous steps for specifying additional feeds from the same service or a different service.</span></span>  
  
     <span data-ttu-id="3f094-151">Cada documento de servicio de datos se procesa como una única operación.</span><span class="sxs-lookup"><span data-stu-id="3f094-151">Each data service document is processed as a single operation.</span></span> <span data-ttu-id="3f094-152">De forma asincrónica se generarán todas las fuentes de distribución de datos en el documento y se volverán a una aplicación cliente en la misma operación.</span><span class="sxs-lookup"><span data-stu-id="3f094-152">All of the data feeds in the document will be generated asynchronously and returned to a client application in the same operation.</span></span> <span data-ttu-id="3f094-153">Por esta razón, especifique solo los pares de tabla y dirección URL para las fuentes de distribución de datos que desee utilizar conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="3f094-153">For this reason, only specify the URL-table pairs for data feeds that you want to use together.</span></span>  
  
     <span data-ttu-id="3f094-154">Dado que los esquemas de autenticación se establecen en el nivel de documento de servicio de datos, cada fuente de distribución de datos adicional debe originarse a partir del servicio o aplicación que admita el mismo esquema de autenticación que la primera fuente.</span><span class="sxs-lookup"><span data-stu-id="3f094-154">Because authentication schemes are set at the data service document level, each additional data feed must originate from service or application that supports the same authentication scheme as the first feed.</span></span> <span data-ttu-id="3f094-155">Todas las fuentes dentro del mismo documento de servicio de datos se autenticarán en tiempo de ejecución bajo el mismo método.</span><span class="sxs-lookup"><span data-stu-id="3f094-155">All feeds within the same data service document will be authenticated under the same method at run time.</span></span>  
  
6.  <span data-ttu-id="3f094-156">Guarde el documento.</span><span class="sxs-lookup"><span data-stu-id="3f094-156">Save the document.</span></span> <span data-ttu-id="3f094-157">El documento de servicio de datos se almacena como archivo físico (.atomsvc) en una biblioteca de contenido que se configura para este tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="3f094-157">The data service document is stored as a physical file (.atomsvc) in a content library that is configured for this content type.</span></span>  
  
 <span data-ttu-id="3f094-158">Para utilizar el documento de servicio de datos, puede abrir un libro de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] en [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] y elegir la opción **Desde fuente de distribución de datos** en el Asistente para importar datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-158">To use the data service document, you can open an [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbook in the [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] and choose the **From Data Feed** option in the Import Data wizard.</span></span> <span data-ttu-id="3f094-159">Cuando se pida, un usuario especificará la dirección URL de SharePoint correspondiente al documento de servicio de datos para iniciar una operación de importación de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-159">When prompted, a user will specify the SharePoint URL of the data service document to start a data import operation.</span></span> <span data-ttu-id="3f094-160">Para obtener más información, vea [usar fuentes de datos &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="3f094-160">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>  
  
##  <a name="secure-a-data-service-document"></a><a name="securedsdoc"></a><span data-ttu-id="3f094-161">Proteger un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-161">Secure a Data Service Document</span></span>  
 <span data-ttu-id="3f094-162">En un documento de servicio de datos se heredan los permisos de la biblioteca que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="3f094-162">A data service document inherits the permissions of the library that contains it.</span></span> <span data-ttu-id="3f094-163">Los permisos que establezca en el elemento determinarán si un usuario puede abrir, modificar o eliminar el documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-163">Permissions that you set on the item will determine whether a user can open, modify or delete the data service document.</span></span>  
  
 <span data-ttu-id="3f094-164">Para utilizar un documento de servicio de datos como una importación de fuentes de distribución de datos en la aplicación cliente de PowerPivot, un usuario solo necesita permisos para ver el documento.</span><span class="sxs-lookup"><span data-stu-id="3f094-164">To use a data service document as a data feed import in the PowerPivot client application, a user only needs view permissions on the document.</span></span> <span data-ttu-id="3f094-165">Estos permisos son suficientes para resolver la dirección URL en el asistente para la importación.</span><span class="sxs-lookup"><span data-stu-id="3f094-165">View permissions are sufficient to resolve the URL in the Import Wizard.</span></span>  
  
 <span data-ttu-id="3f094-166">Los permisos para ver en un documento de servicio de datos solo se comprueban cuando comienza una operación de importación de la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-166">View permissions on a data service document are checked only when a data feed import operation begins.</span></span> <span data-ttu-id="3f094-167">Después de la importación, los permisos en el documento no se comprueban de forma continuada; las fuentes que se agregaron a un origen de datos PowerPivot existen como datos estáticos, desconectados del documento de servicio de datos que proporcionó la información en línea original.</span><span class="sxs-lookup"><span data-stu-id="3f094-167">Post-import, permissions on the document are not checked on an ongoing basis; feeds that were added to a PowerPivot data source exist as static data, disconnected from the data service document that provided the original connection information.</span></span>  
  
 <span data-ttu-id="3f094-168">De igual forma, cualquier operación de actualización de datos que programe posteriormente también excluye el documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-168">Similarly, any data refresh operations that you subsequently schedule also exclude the data service document.</span></span> <span data-ttu-id="3f094-169">En el momento de la importación, la información de conexión para cada fuente se copia en el origen de datos PowerPivot para la actualización.</span><span class="sxs-lookup"><span data-stu-id="3f094-169">At the time of import, connection information for each feed is copied into the PowerPivot data source for refresh purposes.</span></span> <span data-ttu-id="3f094-170">Por tanto, los permisos en un documento de servicio de datos no se comprueban para la actualización de datos, porque nunca se hace referencia al propio documento en una operación de actualización.</span><span class="sxs-lookup"><span data-stu-id="3f094-170">As such, permissions on a data service document are not checked for data refresh, because the document itself is never referenced in a refresh operation.</span></span>  
  
|<span data-ttu-id="3f094-171">Tarea</span><span class="sxs-lookup"><span data-stu-id="3f094-171">Task</span></span>|<span data-ttu-id="3f094-172">Requisitos de permisos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3f094-172">SharePoint permission requirements</span></span>|  
|----------|----------------------------------------|  
|<span data-ttu-id="3f094-173">Importar fuentes de distribución de datos a un libro habilitado para PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="3f094-173">Import data feeds to a PowerPivot-enabled workbook.</span></span>|<span data-ttu-id="3f094-174">Ver los permisos para el documento de servicio de datos en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3f094-174">View permissions to the data service document in a library.</span></span>|  
|<span data-ttu-id="3f094-175">En la aplicación cliente de PowerPivot, actualizar los datos que se recuperaron previamente a través de una fuente.</span><span class="sxs-lookup"><span data-stu-id="3f094-175">In the PowerPivot client application, refresh data that was previously retrieved via a feed.</span></span>|<span data-ttu-id="3f094-176">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3f094-176">Not applicable.</span></span> <span data-ttu-id="3f094-177">La aplicación cliente de PowerPivot utiliza la información de la conexión HTTP incrustada para conectarse directamente a los servicios de datos y aplicaciones que proporcionan la fuente.</span><span class="sxs-lookup"><span data-stu-id="3f094-177">The PowerPivot client application uses embedded HTTP connection information to connect directly to the data services and applications that provide the feed.</span></span> <span data-ttu-id="3f094-178">La aplicación cliente de PowerPivot no utiliza el documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-178">The PowerPivot client application does not use the data service document.</span></span>|  
|<span data-ttu-id="3f094-179">En una granja de servidores de SharePoint, actualice los datos como una tarea programada, sin que se requiera la entrada de datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3f094-179">In a SharePoint farm, refresh data as a scheduled task, with no user input required.</span></span>|<span data-ttu-id="3f094-180">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3f094-180">Not applicable.</span></span> <span data-ttu-id="3f094-181">El servicio PowerPivot utiliza la información de la conexión HTTP incrustada para conectarse directamente a los servicios de datos y aplicaciones que proporcionan la fuente.</span><span class="sxs-lookup"><span data-stu-id="3f094-181">The PowerPivot service uses embedded HTTP connection information to connect directly to the data services and applications that provide the feed.</span></span> <span data-ttu-id="3f094-182">El servicio PowerPivot no utiliza el documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-182">The PowerPivot service does not use the data service document.</span></span>|  
|<span data-ttu-id="3f094-183">Eliminar un documento de servicio de datos en una biblioteca</span><span class="sxs-lookup"><span data-stu-id="3f094-183">Delete a data service document in a library</span></span>|<span data-ttu-id="3f094-184">Permisos de contribución en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3f094-184">Contribute permissions on the library.</span></span>|  
  
##  <a name="modify-a-data-service-document"></a><a name="modifydsdoc"></a> <span data-ttu-id="3f094-185">Modificar un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-185">Modify a Data Service Document</span></span>  
 <span data-ttu-id="3f094-186">Puede agregar, modificar o quitar entradas individuales de tablas de direcciones URL en un documento de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-186">You can add, edit, or remove individual URL-table entries in a data service document.</span></span> <span data-ttu-id="3f094-187">Después de guardar los cambios, los usuarios que seleccionan el documento de servicio en una nueva operación de importación obtendrán las fuentes de los datos que especificó.</span><span class="sxs-lookup"><span data-stu-id="3f094-187">After you save your changes, users who select the service document in a new import operation will get the data feeds you specified.</span></span>  
  
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="3f094-188">que utilizaban una versión anterior del documento no se verán afectados por los cambios que realice.</span><span class="sxs-lookup"><span data-stu-id="3f094-188">workbooks that used a previous version of the document are unaffected by any changes you make.</span></span> <span data-ttu-id="3f094-189">Esto se debe a que un documento de servicio de datos solo se lee una vez durante la operación de importación inicial.</span><span class="sxs-lookup"><span data-stu-id="3f094-189">This is because a data service document is read only once during the initial import operation.</span></span> <span data-ttu-id="3f094-190">Durante la importación, la dirección URL del servicio y los nombres de tabla se copian y almacenan internamente en el libro.</span><span class="sxs-lookup"><span data-stu-id="3f094-190">During the import, service URL and table names are copied and stored internally in the workbook.</span></span> <span data-ttu-id="3f094-191">A continuación, estos valores internos se utilizan en las operaciones de actualización subsiguientes para actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="3f094-191">These internal values are then used in subsequent refresh operations to get updated data.</span></span>  
  
 <span data-ttu-id="3f094-192">Dado que no hay ningún vínculo persistente entre un documento de servicio de datos en un sitio de SharePoint y el libro de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] que contiene la fuente importada, modificar cualquier parte de un documento de servicio de datos no tiene ningún efecto en los libros de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] existentes.</span><span class="sxs-lookup"><span data-stu-id="3f094-192">Because there is no persistent link between a data service document on a SharePoint site and the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbook that contains the imported feed, modifying any part of a data service document has no effect on existing [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3f094-193">Aunque el documento de servicio de datos se lee solo una vez, para obtener las fuentes más recientes se puede tener acceso a los servicios de datos que proporcionan los datos reales a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="3f094-193">Although the data service document is read only once, data services that provide the actual data can be accessed at regular intervals to get newer feeds.</span></span> <span data-ttu-id="3f094-194">Para obtener más información sobre cómo actualizar los datos, vea [actualización de datos PowerPivot](power-pivot-data-refresh.md).</span><span class="sxs-lookup"><span data-stu-id="3f094-194">For more information about how to refresh data, see [PowerPivot Data Refresh](power-pivot-data-refresh.md).</span></span>  
  
##  <a name="next-step-use-a-data-service-document"></a><a name="usedsdoc"></a> <span data-ttu-id="3f094-195">Paso siguiente: usar un documento de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="3f094-195">Next Step: Use a Data Service Document</span></span>  
 <span data-ttu-id="3f094-196">Para utilizar un documento de servicio de datos creado en una biblioteca de SharePoint, use la opción **de importación de fuentes de datos** en un origen de datos PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="3f094-196">To use a data service document that you created in a SharePoint library, you use the **From Data Feeds** import option in a PowerPivot data source.</span></span> <span data-ttu-id="3f094-197">Para obtener instrucciones, vea [usar fuentes de datos &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="3f094-197">For instructions, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f094-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f094-198">See Also</span></span>  
 [<span data-ttu-id="3f094-199">Fuentes de distribución de datos de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="3f094-199">PowerPivot Data Feeds</span></span>](power-pivot-data-feeds.md)  
  
  