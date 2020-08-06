---
title: Inicio de sesión de Reporting Services (cuadro de diálogo de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747959"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a><span data-ttu-id="9b531-102">Inicio de sesión de Reporting Services (cuadro de diálogo de SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b531-102">Reporting Services Login Dialog Box (SSRS)</span></span>
  <span data-ttu-id="9b531-103">Utilice el cuadro de diálogo **Inicio de sesión de Reporting Services** para proporcionar credenciales para publicar informes en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9b531-103">Use the **Reporting Services Login** dialog box to provide credentials to publish reports to the report server.</span></span>  
  
-   <span data-ttu-id="9b531-104">**Nota:** Si es la primera vez que publica un informe en un servidor de informes desde que estableció la propiedad de implementación **TargetServerURL** para un proyecto, compruebe que el nombre del servidor que especificó es similar a `http://localhost/reportserver` , y no `http://localhost/reports` .</span><span class="sxs-lookup"><span data-stu-id="9b531-104">**Note** If this is the first time you have published a report to a report server since set you set the deployment property **TargetServerURL** for a project, verify that the server name you specified is similar to `http://localhost/reportserver`, and not `http://localhost/reports`.</span></span> <span data-ttu-id="9b531-105">La consecuencia indirecta de especificar el directorio `reports` del servidor local en lugar del directorio `reportserver` es la apertura de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9b531-105">Specifying the `reports` directory on the local server instead of the `reportserver` directory indirectly causes this dialog box to open.</span></span> <span data-ttu-id="9b531-106">Para más información sobre cómo establecer **TargetServerURL**, vea [Establecer propiedades de implementación&#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b531-106">For more information about setting **TargetServerURL**, see [Set Deployment Properties &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b531-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="9b531-107">Options</span></span>  
 <span data-ttu-id="9b531-108">**Server**</span><span class="sxs-lookup"><span data-stu-id="9b531-108">**Server**</span></span>  
 <span data-ttu-id="9b531-109">Muestra el nombre del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9b531-109">Displays the name of the report server.</span></span> <span data-ttu-id="9b531-110">Por ejemplo, `http://localhost/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="9b531-110">For example, `http://localhost/reportserver`.</span></span> <span data-ttu-id="9b531-111">Si los servidores de informes usan un puerto distinto del predeterminado, el puerto 80, incluya el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="9b531-111">For report servers that use a different port than default port 80, include the port number.</span></span> <span data-ttu-id="9b531-112">Por ejemplo, `http://localhost:81/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="9b531-112">For example, `http://localhost:81/reportserver`.</span></span>  
  
 <span data-ttu-id="9b531-113">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="9b531-113">**User name**</span></span>  
 <span data-ttu-id="9b531-114">Escriba el nombre de usuario con el que iniciar sesión en el servicio web.</span><span class="sxs-lookup"><span data-stu-id="9b531-114">Type the user name to log in to the Web service.</span></span>  
  
 <span data-ttu-id="9b531-115">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="9b531-115">**Password**</span></span>  
 <span data-ttu-id="9b531-116">Escriba la contraseña con la que iniciar sesión en el servicio web.</span><span class="sxs-lookup"><span data-stu-id="9b531-116">Type the password to log in to the Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b531-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b531-117">See Also</span></span>  
 <span data-ttu-id="9b531-118">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="9b531-118">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="9b531-119">[Especificar información de credenciales y conexión para los orígenes de datos de informe](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Diseñador de informes ayuda F1](report-designer-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="9b531-119">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer F1 Help](report-designer-f1-help.md)</span></span>  
  
  
