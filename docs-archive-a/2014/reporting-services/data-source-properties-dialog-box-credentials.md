---
title: Propiedades del origen de datos (cuadro de diálogo), credenciales | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.credentials.f1
- "10100"
ms.assetid: 14c3eeb6-d37b-4fda-967b-43afcdb48119
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 491da16e6cd38db54c4d27bd8497ca7fdfaae5b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673541"
---
# <a name="data-source-properties-dialog-box-credentials"></a><span data-ttu-id="5b17b-102">Propiedades del origen de datos (cuadro de diálogo), Credenciales</span><span class="sxs-lookup"><span data-stu-id="5b17b-102">Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="5b17b-103">Seleccione **Credenciales** en el cuadro de diálogo **Propiedades del origen de datos** para mostrar y modificar las credenciales para conectarse a un origen de datos en el informe.</span><span class="sxs-lookup"><span data-stu-id="5b17b-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to a data source in the report.</span></span> <span data-ttu-id="5b17b-104">Las credenciales que proporcione se usarán para tener acceso al origen de datos y almacenar en caché una copia de los datos para la vista previa de los informes.</span><span class="sxs-lookup"><span data-stu-id="5b17b-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="5b17b-105">Para obtener más información sobre cómo almacenar en caché datos de la vista previa, vea [Obtener la vista previa de informes](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="5b17b-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="5b17b-106">Para obtener más información sobre las credenciales, vea [Especificar información de credenciales y conexión para los orígenes de datos de informes](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5b17b-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5b17b-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="5b17b-107">Options</span></span>  
 <span data-ttu-id="5b17b-108">**Utilizar autenticación de Windows (seguridad integrada)**</span><span class="sxs-lookup"><span data-stu-id="5b17b-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="5b17b-109">Seleccione esta opción para utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5b17b-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="5b17b-110">**Usar este nombre de usuario y esta contraseña**</span><span class="sxs-lookup"><span data-stu-id="5b17b-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="5b17b-111">Seleccione esta opción para proporcionar un nombre de usuario y una contraseña específicos.</span><span class="sxs-lookup"><span data-stu-id="5b17b-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="5b17b-112">Para los orígenes de datos compartidos: al publicar el proyecto de servidor de informes en el servidor de destino, el nombre de usuario y la contraseña se guardan como las credenciales almacenadas para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b17b-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="5b17b-113">Si desea usar el nombre de usuario y la contraseña como credenciales de Windows, puede editar las propiedades del origen de datos compartido publicado en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="5b17b-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="5b17b-114">Para más información, vea [Crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5b17b-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="5b17b-115">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="5b17b-115">**User name**</span></span>  
 <span data-ttu-id="5b17b-116">Escriba un nombre de usuario con el que iniciar sesión en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5b17b-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="5b17b-117">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="5b17b-117">**Password**</span></span>  
 <span data-ttu-id="5b17b-118">Escriba una contraseña con la que iniciar sesión en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5b17b-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="5b17b-119">**Prompt for credentials** (Pedir credenciales)</span><span class="sxs-lookup"><span data-stu-id="5b17b-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="5b17b-120">Seleccione esta opción para solicitar las credenciales al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="5b17b-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="5b17b-121">**Escriba la cadena del mensaje**</span><span class="sxs-lookup"><span data-stu-id="5b17b-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="5b17b-122">Escriba una frase para pedir al usuario que proporcione las credenciales de inicio de sesión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5b17b-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="5b17b-123">**Sin credenciales**</span><span class="sxs-lookup"><span data-stu-id="5b17b-123">**No credentials**</span></span>  
 <span data-ttu-id="5b17b-124">Seleccione esta opción si no desea proporcionar credenciales para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5b17b-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="5b17b-125">Esta opción solo funciona si el origen de datos no acepta credenciales o si se pasan credenciales de otra manera.</span><span class="sxs-lookup"><span data-stu-id="5b17b-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b17b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b17b-126">See Also</span></span>  
 <span data-ttu-id="5b17b-127">[Propiedades del origen de datos (cuadro de diálogo), general](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span><span class="sxs-lookup"><span data-stu-id="5b17b-127">[Data Source Properties Dialog Box, General](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span></span>  
 <span data-ttu-id="5b17b-128">[Especificar información de credenciales y conexión para los orígenes de datos de informes](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="5b17b-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="5b17b-129">Data Connections, Data Sources, and Connection Strings in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5b17b-129">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
