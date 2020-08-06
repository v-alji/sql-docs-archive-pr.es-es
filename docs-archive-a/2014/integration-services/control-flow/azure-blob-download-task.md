---
title: Tarea de descarga de blobs de Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744815"
---
# <a name="azure-blob-download-task"></a><span data-ttu-id="5509b-102">Tarea de descarga de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="5509b-102">Azure Blob Download Task</span></span>
  <span data-ttu-id="5509b-103">La tarea de descarga de blobs de Azure permite a un paquete SSIS descargar archivos desde un almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="5509b-103">The Azure Blob Download Task enables an SSIS package to download files from an Azure blob storage.</span></span>   
<span data-ttu-id="5509b-104">Para agregar una **tarea de descarga de blobs de Azure**, arrástrela y suéltela en el Diseñador SSIS y haga doble clic (o haga clic con el botón derecho y, después, haga clic en **Editar** ) para ver el siguiente cuadro de diálogo del **Editor de la tarea de descarga de blobs de Azure** .</span><span class="sxs-lookup"><span data-stu-id="5509b-104">To add an **Azure Blob Download Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Download Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="5509b-105">En la tabla siguiente se proporciona la descripción de los campos de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5509b-105">The following table provides description for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5509b-106">**Campo**</span><span class="sxs-lookup"><span data-stu-id="5509b-106">**Field**</span></span>|<span data-ttu-id="5509b-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5509b-107">**Description**</span></span>|  
|<span data-ttu-id="5509b-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="5509b-108">AzureStorageConnection</span></span>|<span data-ttu-id="5509b-109">Especifique un administrador de conexiones de almacenamiento de Azure existente o cree uno nuevo que haga referencia a una cuenta de almacenamiento de Azure, que esté orientado a la ubicación en la que se encuentran hospedados los archivos de blob.</span><span class="sxs-lookup"><span data-stu-id="5509b-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="5509b-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="5509b-110">BlobContainer</span></span>|<span data-ttu-id="5509b-111">Especifica el nombre del contenedor de blobs que contiene los archivos de blob que hay que descargar.</span><span class="sxs-lookup"><span data-stu-id="5509b-111">Specifies the name of the blob container that contains the blob files to be downloaded.</span></span>|  
|<span data-ttu-id="5509b-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="5509b-112">BlobDirectory</span></span>|<span data-ttu-id="5509b-113">Especifica el directorio de blobs que contiene los archivos de blob que hay que descargar.</span><span class="sxs-lookup"><span data-stu-id="5509b-113">Specifies the blob directory that contains the blob files to be downloaded.</span></span> <span data-ttu-id="5509b-114">El directorio de blobs es una estructura jerárquica virtual.</span><span class="sxs-lookup"><span data-stu-id="5509b-114">The blob directory is a virtual hierarchical structure.</span></span>|  
|<span data-ttu-id="5509b-115">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="5509b-115">LocalDirectory</span></span>|<span data-ttu-id="5509b-116">Especifica el directorio local en el que se almacenarán los archivos de blob descargados.</span><span class="sxs-lookup"><span data-stu-id="5509b-116">Specifies the local directory where the downloaded blob files will be stored.</span></span>|  
|<span data-ttu-id="5509b-117">FileName</span><span class="sxs-lookup"><span data-stu-id="5509b-117">FileName</span></span>|<span data-ttu-id="5509b-118">Especifica un nombre de filtro para seleccionar archivos con el patrón de nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="5509b-118">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="5509b-119">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="5509b-119">E.g.</span></span> <span data-ttu-id="5509b-120">MiHoja\*.xls\* incluirá archivos como MiHoja001.xls y MiHojaABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="5509b-120">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="5509b-121">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="5509b-121">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="5509b-122">Especifica un filtro de intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5509b-122">Specifies a time range filter.</span></span> <span data-ttu-id="5509b-123">Se incluirán los archivos modificados después de **TimeRangeFrom** y antes de **TimeRangeTo** .</span><span class="sxs-lookup"><span data-stu-id="5509b-123">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
