---
title: Tarea de carga de blobs de Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobuptask.f1
- sql11.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ca15c5a77a2694293981121f4e5927be8ec0e1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744814"
---
# <a name="azure-blob-upload-task"></a><span data-ttu-id="cb56f-102">Tarea de carga de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="cb56f-102">Azure Blob Upload Task</span></span>
  <span data-ttu-id="cb56f-103">La tarea de carga de blobs de Azure permite a un paquete SSIS cargar archivos a un almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="cb56f-103">The Azure Blob Upload Task enables an SSIS package to upload files to an Azure blob storage.</span></span>   
<span data-ttu-id="cb56f-104">Para agregar una **tarea de carga de blobs de Azure**, arrástrela y colóquela en el Diseñador SSIS, haga doble clic o haga clic con el botón derecho y, luego, haga clic en **Editar** para ver el siguiente cuadro de diálogo del **Azure Blob Upload Task Editor** (Editor de la tarea de carga de blobs de Azure).</span><span class="sxs-lookup"><span data-stu-id="cb56f-104">To add an **Azure Blob Upload Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Upload Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="cb56f-105">En la tabla siguiente se proporcionan las descripciones de los campos de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cb56f-105">The following table provides descriptions for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb56f-106">**Campo**</span><span class="sxs-lookup"><span data-stu-id="cb56f-106">**Field**</span></span>|<span data-ttu-id="cb56f-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cb56f-107">**Description**</span></span>|  
|<span data-ttu-id="cb56f-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="cb56f-108">AzureStorageConnection</span></span>|<span data-ttu-id="cb56f-109">Especifique un administrador de conexiones de almacenamiento de Azure existente o cree uno nuevo que haga referencia a una cuenta de almacenamiento de Azure, que esté orientado a la ubicación en la que se encuentran hospedados los archivos de blob.</span><span class="sxs-lookup"><span data-stu-id="cb56f-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="cb56f-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="cb56f-110">BlobContainer</span></span>|<span data-ttu-id="cb56f-111">Especifica el nombre del contenedor de blobs que contendrá los archivos cargados como blobs.</span><span class="sxs-lookup"><span data-stu-id="cb56f-111">Specifies the name of the blob container that will hold the uploaded files as blobs.</span></span>|  
|<span data-ttu-id="cb56f-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="cb56f-112">BlobDirectory</span></span>|<span data-ttu-id="cb56f-113">Especifica el directorio de blobs donde se almacenará el archivo cargado como un blob en bloques.</span><span class="sxs-lookup"><span data-stu-id="cb56f-113">Specifies the blob directory where the uploaded file will be stored as a block blob.</span></span> <span data-ttu-id="cb56f-114">El directorio de blobs es una estructura jerárquica virtual.</span><span class="sxs-lookup"><span data-stu-id="cb56f-114">The blob directory is a virtual hierarchical structure.</span></span> <span data-ttu-id="cb56f-115">Si ya existe el blob, se reemplazará.</span><span class="sxs-lookup"><span data-stu-id="cb56f-115">If the blob already exists, it will be replaced.</span></span>|  
|<span data-ttu-id="cb56f-116">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="cb56f-116">LocalDirectory</span></span>|<span data-ttu-id="cb56f-117">Especifica el directorio local que contiene los archivos que se van a cargar.</span><span class="sxs-lookup"><span data-stu-id="cb56f-117">Specify the local directory that contains the files to be uploaded.</span></span>|  
|<span data-ttu-id="cb56f-118">FileName</span><span class="sxs-lookup"><span data-stu-id="cb56f-118">FileName</span></span>|<span data-ttu-id="cb56f-119">Especifica un nombre de filtro para seleccionar archivos con el patrón de nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="cb56f-119">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="cb56f-120">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="cb56f-120">E.g.</span></span> <span data-ttu-id="cb56f-121">MiHoja\*.xls\* incluirá archivos como MiHoja001.xls y MiHojaABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="cb56f-121">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="cb56f-122">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="cb56f-122">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="cb56f-123">Especifica un filtro de intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="cb56f-123">Specifies a time range filter.</span></span> <span data-ttu-id="cb56f-124">Se incluirán los archivos modificados después de **TimeRangeFrom** y antes de **TimeRangeTo** .</span><span class="sxs-lookup"><span data-stu-id="cb56f-124">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
