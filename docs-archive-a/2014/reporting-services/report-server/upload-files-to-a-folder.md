---
title: Cargar archivos a una carpeta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
- files [Reporting Services]
- folders [Reporting Services], uploading files to
ms.assetid: 2f99a288-d4aa-4c64-b310-e457a2aef2c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfb595ed6059436d17cb82262f5d1975a8397dbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672610"
---
# <a name="upload-files-to-a-folder"></a><span data-ttu-id="96a3a-102">Cargar archivos a una carpeta</span><span class="sxs-lookup"><span data-stu-id="96a3a-102">Upload Files to a Folder</span></span>
  <span data-ttu-id="96a3a-103">Puede cargar archivos desde el sistema de archivos y almacenarlos en una base de datos del servidor de informes como elementos administrados.</span><span class="sxs-lookup"><span data-stu-id="96a3a-103">You can upload files from the file system and store them as managed items in a report server database.</span></span> <span data-ttu-id="96a3a-104">Lo que sucede al cargar el archivo depende del tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="96a3a-104">What happens when you upload a file depends on the file type.</span></span>

-   <span data-ttu-id="96a3a-105">Cargar un archivo .rdl equivale a publicar un informe.</span><span class="sxs-lookup"><span data-stu-id="96a3a-105">Uploading an .rdl file is equivalent to publishing a report.</span></span>

-   <span data-ttu-id="96a3a-106">Al cargar cualquier otro tipo de archivo, éste se agrega a la base de datos del servidor de informes como un objeto binario único.</span><span class="sxs-lookup"><span data-stu-id="96a3a-106">Uploading any other file adds it to the report server database as a single binary object.</span></span> <span data-ttu-id="96a3a-107">Estos archivos se publican en un servidor de informes como recurso.</span><span class="sxs-lookup"><span data-stu-id="96a3a-107">These files are published to a report server as a resource.</span></span> <span data-ttu-id="96a3a-108">Los recursos pueden ser cualquier tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="96a3a-108">Resources can be any file type.</span></span> <span data-ttu-id="96a3a-109">Si la extensión de archivo corresponde a la de un tipo MIME conocido, se utilizará un icono de dicho tipo MIME para identificar el tipo de recurso.</span><span class="sxs-lookup"><span data-stu-id="96a3a-109">If the file extension matches a known MIME type, an icon for that MIME type is used to identify the resource type.</span></span> <span data-ttu-id="96a3a-110">De lo contrario, los recursos se indican mediante un icono de archivo genérico.</span><span class="sxs-lookup"><span data-stu-id="96a3a-110">Otherwise, a generic file icon indicates a resource.</span></span>

> [!NOTE]
>  <span data-ttu-id="96a3a-111">No se pueden cargar archivos de origen de datos de informes (.rds) para crear un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="96a3a-111">You cannot upload a report data source (.rds) file to create a shared data source.</span></span> <span data-ttu-id="96a3a-112">Los archivos .rds solo se utilizan en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="96a3a-112">An .rds file is used only in Report Designer.</span></span> <span data-ttu-id="96a3a-113">No puede proporcionar el contenido para un elemento de origen de datos compartido que se defina y administre mediante el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="96a3a-113">It cannot provide the content for a shared data source item that you define and manage through Report Manager.</span></span> <span data-ttu-id="96a3a-114">Como alternativa a la carga, se puede escribir un script que cree un origen de datos compartido basado en un archivo .rds.</span><span class="sxs-lookup"><span data-stu-id="96a3a-114">As an alternative to uploading, you can write a script that creates a shared data source based on a .rds file.</span></span>

 <span data-ttu-id="96a3a-115">[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]determina el tamaño de archivo máximo para los elementos cargados.</span><span class="sxs-lookup"><span data-stu-id="96a3a-115">The maximum file size for uploaded items is determined by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="96a3a-116">De manera predeterminada, el tamaño máximo es de 4 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="96a3a-116">By default, the maximum size is 4 megabytes (MB).</span></span>

 <span data-ttu-id="96a3a-117">Visualmente, los archivos que se cargan a la base de datos del servidor de informes aparecen representados en la jerarquía de carpetas con los siguientes iconos.</span><span class="sxs-lookup"><span data-stu-id="96a3a-117">Visually, files that you upload to a report server database are represented in the folder hierarchy with the following icons.</span></span>

 <span data-ttu-id="96a3a-118">Icono de informe ![icono](../media/hlp-16doc.gif "Icono de informe") de informe</span><span class="sxs-lookup"><span data-stu-id="96a3a-118">![Report icon](../media/hlp-16doc.gif "Report icon") report icon</span></span>

 <span data-ttu-id="96a3a-119">Icono de ![modelo](../media/model-icon.gif "Icono de modelo") icono de modelo de informe</span><span class="sxs-lookup"><span data-stu-id="96a3a-119">![Model icon](../media/model-icon.gif "Model icon") report model icon</span></span>

 <span data-ttu-id="96a3a-120">icono de ![recurso genérico](../media/hlp-16file.gif "Icono de recurso genérico") icono de recurso genérico</span><span class="sxs-lookup"><span data-stu-id="96a3a-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon") generic resource icon</span></span>

 <span data-ttu-id="96a3a-121">Al cargar un archivo, éste se sitúa siempre en la carpeta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="96a3a-121">When you upload a file, it is always placed in the folder that is currently selected.</span></span> <span data-ttu-id="96a3a-122">Puede navegar en primer lugar hasta la carpeta en la que desea hospedar el elemento o bien puede cargar el archivo y moverlo después a la ubicación final.</span><span class="sxs-lookup"><span data-stu-id="96a3a-122">You can navigate to the folder that you want to contain the item first, or you can upload a file and then move it to a final location later.</span></span>

 <span data-ttu-id="96a3a-123">Para cargar un archivo, use el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="96a3a-123">To upload a file, use Report Manager.</span></span> <span data-ttu-id="96a3a-124">Podrá cargar archivos a un servidor de informes dependiendo de qué tareas formen parte de su asignación de roles.</span><span class="sxs-lookup"><span data-stu-id="96a3a-124">Whether you can upload files to a report server depends on tasks that are part of your role assignment.</span></span> <span data-ttu-id="96a3a-125">Si utiliza la seguridad predeterminada, solo los administradores locales podrán agregar elementos a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="96a3a-125">If you are using default security, local administrators can add items to a report server.</span></span> <span data-ttu-id="96a3a-126">Si está habilitado el rol Mis informes, cada usuario que disponga de una carpeta Mis informes tendrá permiso para cargar archivos a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="96a3a-126">If My Reports is enabled, any user who has a My Reports folder has permission to upload items to that folder.</span></span> <span data-ttu-id="96a3a-127">Si utiliza asignaciones de roles personalizados, deberán incluir las tareas compatibles con la administración de carpetas.</span><span class="sxs-lookup"><span data-stu-id="96a3a-127">If you use custom role assignments, the role assignment must include tasks that support folder management.</span></span>

|<span data-ttu-id="96a3a-128">Para hacer esto</span><span class="sxs-lookup"><span data-stu-id="96a3a-128">To do this</span></span>|<span data-ttu-id="96a3a-129">Incluya estas tareas</span><span class="sxs-lookup"><span data-stu-id="96a3a-129">Include these tasks</span></span>|
|----------------|-------------------------|
|<span data-ttu-id="96a3a-130">Cargar un archivo .rdl a una carpeta</span><span class="sxs-lookup"><span data-stu-id="96a3a-130">Upload an .rdl file to a folder</span></span>|<span data-ttu-id="96a3a-131">Administrar informes</span><span class="sxs-lookup"><span data-stu-id="96a3a-131">Manage reports</span></span>|
|<span data-ttu-id="96a3a-132">Cargar cualquier archivo como objeto binario</span><span class="sxs-lookup"><span data-stu-id="96a3a-132">Upload any file as a binary object</span></span>|<span data-ttu-id="96a3a-133">Administrar recursos</span><span class="sxs-lookup"><span data-stu-id="96a3a-133">Manage resources</span></span>|
|<span data-ttu-id="96a3a-134">Ver el contenido de una carpeta</span><span class="sxs-lookup"><span data-stu-id="96a3a-134">View the contents of a folder</span></span>|<span data-ttu-id="96a3a-135">Ver recursos, Ver informes</span><span class="sxs-lookup"><span data-stu-id="96a3a-135">View resources, View reports</span></span>|

## <a name="see-also"></a><span data-ttu-id="96a3a-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96a3a-136">See Also</span></span>
 <span data-ttu-id="96a3a-137">[Administrador de informes &#40;modo nativo de SSRS&#41;].. /report-manager-ssrs-native-mode.md) [conceder permisos en un servidor de informes en modo nativo](../security/granting-permissions-on-a-native-mode-report-server.md) [tareas y permisos](../security/tasks-and-permissions.md) [cargar un archivo o informe &#40;administrador de informes&#41;](../reports/upload-a-file-or-report-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="96a3a-137">[Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md) [Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Tasks and Permissions](../security/tasks-and-permissions.md) [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span></span>


