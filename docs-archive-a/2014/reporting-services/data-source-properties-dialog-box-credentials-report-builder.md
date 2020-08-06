---
title: Propiedades del origen de datos (cuadro de diálogo), credenciales (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10017"
ms.assetid: 4531f09f-d653-4c05-a120-d7788838bc99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e47ba571e2b0adf2738499c1d027a4edde86e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674631"
---
# <a name="data-source-properties-dialog-box-credentials-report-builder"></a><span data-ttu-id="0e193-102">Propiedades del origen de datos (cuadro de diálogo), Credenciales (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="0e193-102">Data Source Properties Dialog Box, Credentials (Report Builder)</span></span>
  <span data-ttu-id="0e193-103">Seleccione **Credenciales** en el cuadro de diálogo **Propiedades del origen de datos** para mostrar y modificar las credenciales para conectarse a un origen de datos incrustado en el informe.</span><span class="sxs-lookup"><span data-stu-id="0e193-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to an embedded data source in the report.</span></span> <span data-ttu-id="0e193-104">Las credenciales que proporcione se usarán para tener acceso al origen de datos con el fin de obtener una vista previa de los informes.</span><span class="sxs-lookup"><span data-stu-id="0e193-104">The credentials that you provide are used to access the data source for previewing reports.</span></span> <span data-ttu-id="0e193-105">Para obtener más información, vea [Especificar credenciales en el Generador de informes](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="0e193-105">For more information about credentials, see [Specify Credentials in Report Builder](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0e193-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="0e193-106">Options</span></span>  
 <span data-ttu-id="0e193-107">**Utilizar autenticación de Windows (seguridad integrada)**</span><span class="sxs-lookup"><span data-stu-id="0e193-107">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="0e193-108">Seleccione esta opción para utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0e193-108">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="0e193-109">**Usar este nombre de usuario y esta contraseña**</span><span class="sxs-lookup"><span data-stu-id="0e193-109">**Use this user name and password**</span></span>  
 <span data-ttu-id="0e193-110">Seleccione esta opción para proporcionar un nombre de usuario y una contraseña específicos.</span><span class="sxs-lookup"><span data-stu-id="0e193-110">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="0e193-111">Para los orígenes de datos incrustados: al publicar el proyecto del servidor de informes en el servidor de destino, el nombre de usuario y la contraseña se guardan como las credenciales almacenadas para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0e193-111">For embedded data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="0e193-112">Si desea usar el nombre de usuario y la contraseña como credenciales de Windows, puede cambiar las propiedades del origen de datos compartido publicado en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0e193-112">If you want to use the user name and password as Windows credentials, you can change the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="0e193-113">Para obtener más información, vea [Crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) en la documentación de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en los [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Libros en pantalla](https://go.microsoft.com/fwlink/?linkid=121312) de .</span><span class="sxs-lookup"><span data-stu-id="0e193-113">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
 <span data-ttu-id="0e193-114">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="0e193-114">**User name**</span></span>  
 <span data-ttu-id="0e193-115">Escriba un nombre de usuario con el que iniciar sesión en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e193-115">Type a user name to log on to the data source.</span></span>  
  
 <span data-ttu-id="0e193-116">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="0e193-116">**Password**</span></span>  
 <span data-ttu-id="0e193-117">Escriba una contraseña con la que iniciar sesión en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e193-117">Type a password to log on to the data source.</span></span>  
  
 <span data-ttu-id="0e193-118">**Prompt for credentials** (Pedir credenciales)</span><span class="sxs-lookup"><span data-stu-id="0e193-118">**Prompt for credentials**</span></span>  
 <span data-ttu-id="0e193-119">Seleccione esta opción para solicitar las credenciales al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="0e193-119">Select this option to prompt for credentials when the report runs.</span></span>  
  
 <span data-ttu-id="0e193-120">**Escriba la cadena del mensaje**</span><span class="sxs-lookup"><span data-stu-id="0e193-120">**Enter prompt string**</span></span>  
 <span data-ttu-id="0e193-121">Escriba una frase para pedir al usuario que proporcione las credenciales de inicio de sesión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e193-121">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="0e193-122">**Sin credenciales**</span><span class="sxs-lookup"><span data-stu-id="0e193-122">**No credentials**</span></span>  
 <span data-ttu-id="0e193-123">Seleccione esta opción si no desea proporcionar credenciales para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e193-123">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="0e193-124">Esta opción solo funciona si el origen de datos no acepta credenciales o si se pasan credenciales de otra manera.</span><span class="sxs-lookup"><span data-stu-id="0e193-124">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
 <span data-ttu-id="0e193-125">En algunas extensiones de datos, se debe configurar una cuenta de ejecución desatendida en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="0e193-125">From some data extensions, the unattended execution account must be configured on the report server.</span></span>  
  
 <span data-ttu-id="0e193-126">Para obtener más información, vea el tema del tipo de origen de datos correspondiente en [Agregar datos de orígenes de datos externos &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) y [Configurar la cuenta de ejecución desatendida &#40;Administrador de configuración de SSRS&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) en la documentación de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] de los [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Libros en pantalla](https://go.microsoft.com/fwlink/?linkid=121312) de .</span><span class="sxs-lookup"><span data-stu-id="0e193-126">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e193-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e193-127">See Also</span></span>  
 <span data-ttu-id="0e193-128">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="0e193-128">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="0e193-129">[Propiedades del origen de datos (cuadro de diálogo), general &#40;Generador de informes&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="0e193-129">[Data Source Properties Dialog Box, General &#40;Report Builder&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span></span>  
 <span data-ttu-id="0e193-130">[Agregar y comprobar una conexión de datos o un origen de datos &#40;Generador de informes y SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0e193-130">[Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0e193-131">Agregar datos a un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e193-131">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
