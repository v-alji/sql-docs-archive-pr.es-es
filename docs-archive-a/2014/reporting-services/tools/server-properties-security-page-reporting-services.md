---
title: Propiedades del servidor (página de seguridad) - Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.security.f1
ms.assetid: f49aedc6-f145-4df1-8f69-d5d910f492c6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f709d42bf593b4933d9fc1fdc423c195967df382
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674006"
---
# <a name="server-properties-security-page---reporting-services"></a><span data-ttu-id="3f870-102">Propiedades del servidor (página de seguridad) - Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3f870-102">Server Properties (Security Page) - Reporting Services</span></span>
  <span data-ttu-id="3f870-103">Use esta página para desactivar características que pueden poner en peligro un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3f870-103">Use this page to turn off features that can potentially compromise a report server.</span></span> <span data-ttu-id="3f870-104">Al desactivar estas características, se limitará alguna funcionalidad, pero puede mejorar la seguridad total del servidor de informes mitigando amenazas concretas.</span><span class="sxs-lookup"><span data-stu-id="3f870-104">Turning off these features will limit some functionality, but can improve the overall security of the report server by mitigating specific threats.</span></span>  
  
 <span data-ttu-id="3f870-105">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a una instancia del servidor de informes, haga clic con el botón derecho en el nombre del servidor de informes y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3f870-105">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="3f870-106">Haga clic en **Seguridad** para abrir esta página.</span><span class="sxs-lookup"><span data-stu-id="3f870-106">Click **Security** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3f870-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="3f870-107">Options</span></span>  
 <span data-ttu-id="3f870-108">**Habilitar la seguridad integrada de Windows para orígenes de datos de informe**</span><span class="sxs-lookup"><span data-stu-id="3f870-108">**Enable Windows integrated security for report data sources**</span></span>  
 <span data-ttu-id="3f870-109">Especifique si puede realizarse una conexión a un origen de datos de informe con el token de seguridad de Windows del usuario que solicitó el informe.</span><span class="sxs-lookup"><span data-stu-id="3f870-109">Specify whether a connection to a report data source can be made using the Windows security token of the user who requested the report.</span></span>  
  
 <span data-ttu-id="3f870-110">Si desactiva esta característica, la característica de Seguridad integrada de Windows en las páginas de propiedades de origen de dato del informe no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="3f870-110">If you turn off this feature, the Windows Integrated Security feature in the report data source property pages will be unavailable.</span></span> <span data-ttu-id="3f870-111">Si los orígenes de datos del informe se configuran para la seguridad integrada de Windows y desactiva posteriormente esta característica, el servidor de informes actualizará inmediatamente todas las propiedades de conexión a un origen de datos para solicitar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="3f870-111">If report data sources are configured for Windows integrated security and you subsequently turn off this feature, the report server will immediately update all data source connection properties to prompt for credentials.</span></span>  
  
 <span data-ttu-id="3f870-112">**Habilitar la notificación ad hoc**</span><span class="sxs-lookup"><span data-stu-id="3f870-112">**Enable Ad Hoc Reporting**</span></span>  
 <span data-ttu-id="3f870-113">Especifica si los usuarios pueden realizar consultas ad hoc desde un informe del Generador de informes, en el que los nuevos informes se generan automáticamente cuando un usuario hace clic en los datos de interés.</span><span class="sxs-lookup"><span data-stu-id="3f870-113">Specify whether users can perform ad hoc queries from a Report Builder report, where new reports are automatically generated when a user clicks data of interest.</span></span>  
  
 <span data-ttu-id="3f870-114">Al establecer esta opción se determina si la propiedad `EnableLoadReportDefinition` en el servidor de informes está se establece en `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="3f870-114">Setting this option determines whether the `EnableLoadReportDefinition` property on the report server is set to `True` or `False`.</span></span> <span data-ttu-id="3f870-115">Si borra esta opción, la propiedad se establecerá en `False` y el servidor de informes no generará informes click-through que se crean durante la exploración de datos.</span><span class="sxs-lookup"><span data-stu-id="3f870-115">If you clear this option, the property will be set to `False` and report server will not generate clickthrough reports that are created during data exploration.</span></span> <span data-ttu-id="3f870-116">Se bloquearán todas las llamadas al método `LoadReportDefinition`.</span><span class="sxs-lookup"><span data-stu-id="3f870-116">All calls to the `LoadReportDefinition` method will be blocked.</span></span>  
  
 <span data-ttu-id="3f870-117">Al desactivar esta opción, se mitiga una amenaza en la que un usuario malintencionado inicia un ataque por denegación de servicio sobrecargando el servidor de informes con solicitudes `LoadReportDefinition`.</span><span class="sxs-lookup"><span data-stu-id="3f870-117">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with `LoadReportDefinition` requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f870-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f870-118">See Also</span></span>  
 <span data-ttu-id="3f870-119">[Establecer las propiedades del servidor de informes &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3f870-119">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="3f870-120">[Conectarse a un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3f870-120">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="3f870-121">[Especificar información de credenciales y conexión para los orígenes de datos de informes] (.. /Report-Data/Specify-Credential-and-Connection-Information-for-Report-Data-Sources.MD [servidor de informes en Management Studio ayuda de F1](report-server-in-management-studio-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="3f870-121">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md [Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md)</span></span>  
  
  
