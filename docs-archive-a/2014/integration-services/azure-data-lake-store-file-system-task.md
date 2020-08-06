---
title: Tarea Sistema de archivos de Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSTASK.F1
- SQL11.DTS.DESIGNER.AFPADLSTASK.F1
ms.assetid: 02b9edd7-6ef9-463e-abbf-e1830bcae875
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bc37e774c5346190635e50259deb47f2f22a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674291"
---
# <a name="azure-data-lake-store-file-system-task"></a><span data-ttu-id="0de61-102">Tarea Sistema de archivos de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="0de61-102">Azure Data Lake Store File System Task</span></span>

<span data-ttu-id="0de61-103">La **tarea sistema de archivos Azure Data Lake Store** permite a los usuarios realizar varias operaciones del sistema de archivos en [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span><span class="sxs-lookup"><span data-stu-id="0de61-103">The **Azure Data Lake Store File System Task** enables users to perform various file system operations on [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span></span>

<span data-ttu-id="0de61-104">Para agregar una tarea Sistema de archivos de Azure Data Lake Store a un paquete, arrástrela desde el cuadro de herramientas de SSIS al lienzo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="0de61-104">To add an Azure Data Lake Store File System Task to a package, drag it from SSIS Toolbox to the designer canvas.</span></span> <span data-ttu-id="0de61-105">A continuación, haga doble clic en la tarea, o bien haga clic con el botón secundario en la tarea y seleccione **Editar**para abrir el cuadro de diálogo Editor de la tarea.</span><span class="sxs-lookup"><span data-stu-id="0de61-105">Then double-click the task, or right-click the task and select **Edit**, to open the task editor dialog box.</span></span>

<span data-ttu-id="0de61-106">La propiedad **Operación** especifica la operación del sistema de archivos que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="0de61-106">The **Operation** property specifies the file system operation to perform.</span></span> <span data-ttu-id="0de61-107">Es compatible con las siguientes operaciones.</span><span class="sxs-lookup"><span data-stu-id="0de61-107">The following operations are supported.</span></span>

* <span data-ttu-id="0de61-108">**CopyToADLS:** cargar archivos a ADLS.</span><span class="sxs-lookup"><span data-stu-id="0de61-108">**CopyToADLS:** Upload files to ADLS.</span></span>
* <span data-ttu-id="0de61-109">**CopyToADLS:** descargar archivos de ADLS.</span><span class="sxs-lookup"><span data-stu-id="0de61-109">**CopyFromADLS:** Download files from ADLS.</span></span>

<span data-ttu-id="0de61-110">Para cualquier operación, tendrá que especificar un administrador de conexiones de Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="0de61-110">For any operation, you have to specify an Azure Data Lake connection manager.</span></span>

<span data-ttu-id="0de61-111">Estas son las descripciones de las propiedades específicas de cada operación.</span><span class="sxs-lookup"><span data-stu-id="0de61-111">Here are the descriptions of the properties specific to each operation.</span></span>

## <a name="copytoadls"></a><span data-ttu-id="0de61-112">CopyToADLS</span><span class="sxs-lookup"><span data-stu-id="0de61-112">CopyToADLS</span></span>

* <span data-ttu-id="0de61-113">**LocalDirectory:** Especifica el directorio de origen que contiene los archivos que se van a cargar.</span><span class="sxs-lookup"><span data-stu-id="0de61-113">**LocalDirectory:** Specifies the source directory which contains files to upload.</span></span>
* <span data-ttu-id="0de61-114">**FileNamePattern:** especifica un filtro de nombre de archivo para los archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="0de61-114">**FileNamePattern:** Specifies a file name filter for source files.</span></span> <span data-ttu-id="0de61-115">Solo se cargarán los archivos cuyo nombre coincida con el patrón especificado.</span><span class="sxs-lookup"><span data-stu-id="0de61-115">Only files whose name matches the specified pattern will be uploaded.</span></span> <span data-ttu-id="0de61-116">Se admite el uso de los caracteres comodín `*` y `?`.</span><span class="sxs-lookup"><span data-stu-id="0de61-116">Wildcards `*` and `?` are supported.</span></span>
* <span data-ttu-id="0de61-117">**SearchRecursively:** especifica si se deben buscar de forma recursiva en el directorio de origen los archivos para cargar.</span><span class="sxs-lookup"><span data-stu-id="0de61-117">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to upload.</span></span>
* <span data-ttu-id="0de61-118">**AzureDataLakeDirectory:** especifica el directorio de destino de ADLS al que cargar archivos.</span><span class="sxs-lookup"><span data-stu-id="0de61-118">**AzureDataLakeDirectory:** Specifies the ADLS destination directory to upload files to.</span></span>
* <span data-ttu-id="0de61-119">**FileExpiry:** Especifica una fecha y hora de expiración para los archivos cargados en ADLS, o bien deje esta propiedad en blanco para indicar que los archivos nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="0de61-119">**FileExpiry:** Specifies an expiration date and time for the files uploaded to ADLS, or leave this property blank to indicate that the files never expire.</span></span>

## <a name="copyfromadls"></a><span data-ttu-id="0de61-120">CopyFromADLS</span><span class="sxs-lookup"><span data-stu-id="0de61-120">CopyFromADLS</span></span>

* <span data-ttu-id="0de61-121">**AzureDataLakeDirectory:** especifica el directorio de origen de ADLS que contiene los archivos que se descargarán.</span><span class="sxs-lookup"><span data-stu-id="0de61-121">**AzureDataLakeDirectory:** Specifies the ADLS source directory which contains the files to download.</span></span>
* <span data-ttu-id="0de61-122">**SearchRecursively:** especifica si se deben buscar de forma recursiva en el directorio de origen archivos para descargar.</span><span class="sxs-lookup"><span data-stu-id="0de61-122">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to download.</span></span>
* <span data-ttu-id="0de61-123">**LocalDirectory:** especifica el directorio de destino para almacenar los archivos descargados.</span><span class="sxs-lookup"><span data-stu-id="0de61-123">**LocalDirectory:** Specifies the destination directory to store downloaded files.</span></span>
