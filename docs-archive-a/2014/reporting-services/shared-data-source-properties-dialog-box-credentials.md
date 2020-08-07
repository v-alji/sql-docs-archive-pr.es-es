---
title: Propiedades del origen de datos compartido (cuadro de diálogo), credenciales | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shareddatasource.credentials.f1
ms.assetid: c08d1a5f-206b-4d53-ab1a-368b651ee5bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8594c6627c033d31937b2aa8691869cdbba213b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746146"
---
# <a name="shared-data-source-properties-dialog-box-credentials"></a><span data-ttu-id="e42a4-102">Propiedades del origen de datos compartidos (cuadro de diálogo), Credenciales</span><span class="sxs-lookup"><span data-stu-id="e42a4-102">Shared Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="e42a4-103">Seleccione **Credenciales** en el cuadro de diálogo **Propiedades del origen de datos compartidos** para mostrar y modificar las credenciales para conectarse a un origen de datos compartido en el informe.</span><span class="sxs-lookup"><span data-stu-id="e42a4-103">Select **Credentials** on the **Shared Data Source Properties** dialog box to display and modify credentials to connect to a shared data source in the report.</span></span> <span data-ttu-id="e42a4-104">Las credenciales que proporcione se usarán para tener acceso al origen de datos y almacenar en caché una copia de los datos para la vista previa de los informes.</span><span class="sxs-lookup"><span data-stu-id="e42a4-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="e42a4-105">Para obtener más información sobre cómo almacenar en caché datos de la vista previa, vea [Obtener la vista previa de informes](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e42a4-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="e42a4-106">Para obtener más información sobre las credenciales, vea [Especificar información de credenciales y conexión para los orígenes de datos de informes](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e42a4-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e42a4-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="e42a4-107">Options</span></span>  
 <span data-ttu-id="e42a4-108">**Utilizar autenticación de Windows (seguridad integrada)**</span><span class="sxs-lookup"><span data-stu-id="e42a4-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="e42a4-109">Seleccione esta opción para utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e42a4-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e42a4-110">**Usar este nombre de usuario y esta contraseña**</span><span class="sxs-lookup"><span data-stu-id="e42a4-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="e42a4-111">Seleccione esta opción para proporcionar un nombre de usuario y una contraseña específicos.</span><span class="sxs-lookup"><span data-stu-id="e42a4-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="e42a4-112">Para los orígenes de datos compartidos: al publicar el proyecto de servidor de informes en el servidor de destino, el nombre de usuario y la contraseña se guardan como las credenciales almacenadas para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e42a4-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="e42a4-113">Si desea usar el nombre de usuario y la contraseña como credenciales de Windows, puede editar las propiedades del origen de datos compartido publicado en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e42a4-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="e42a4-114">Para más información, vea [Crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e42a4-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="e42a4-115">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="e42a4-115">**User name**</span></span>  
 <span data-ttu-id="e42a4-116">Escriba un nombre de usuario con el que iniciar sesión en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e42a4-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="e42a4-117">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="e42a4-117">**Password**</span></span>  
 <span data-ttu-id="e42a4-118">Escriba una contraseña con la que iniciar sesión en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e42a4-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="e42a4-119">**Prompt for credentials** (Pedir credenciales)</span><span class="sxs-lookup"><span data-stu-id="e42a4-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="e42a4-120">Seleccione esta opción para solicitar las credenciales al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="e42a4-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="e42a4-121">**Escriba la cadena del mensaje**</span><span class="sxs-lookup"><span data-stu-id="e42a4-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="e42a4-122">Escriba una frase para pedir al usuario que proporcione las credenciales de inicio de sesión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e42a4-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="e42a4-123">**Sin credenciales**</span><span class="sxs-lookup"><span data-stu-id="e42a4-123">**No credentials**</span></span>  
 <span data-ttu-id="e42a4-124">Seleccione esta opción si no desea proporcionar credenciales para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e42a4-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="e42a4-125">Esta opción solo funciona si el origen de datos no acepta credenciales o si se pasan credenciales de otra manera.</span><span class="sxs-lookup"><span data-stu-id="e42a4-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42a4-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e42a4-126">See Also</span></span>  
 <span data-ttu-id="e42a4-127">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e42a4-127">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="e42a4-128">[Especificar información de credenciales y conexión para los orígenes de datos de informes](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="e42a4-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="e42a4-129">Propiedades del origen de datos compartidos (cuadro de diálogo), General</span><span class="sxs-lookup"><span data-stu-id="e42a4-129">Shared Data Source Properties Dialog Box, General</span></span>](../../2014/reporting-services/shared-data-source-properties-dialog-box-general.md)  
  
  
