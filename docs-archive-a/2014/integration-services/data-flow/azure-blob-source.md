---
title: Origen de blob de Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobsrc.f1
- sql11.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a14c7022437c8a23f898a0f29c211bd9ae82aa0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676620"
---
# <a name="azure-blob-source"></a><span data-ttu-id="7476c-102">Origen de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="7476c-102">Azure Blob Source</span></span>
 <span data-ttu-id="7476c-103">El componente **Azure Blob Source** (Origen de blobs de Azure) permite que un paquete SSIS lea datos de un blob de Azure.</span><span class="sxs-lookup"><span data-stu-id="7476c-103">The **Azure Blob Source** component enables an SSIS package to read data from an Azure blob.</span></span> <span data-ttu-id="7476c-104">Los formatos de archivo admitidos son: CSV y AVRO.</span><span class="sxs-lookup"><span data-stu-id="7476c-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="7476c-105">Para ver el editor del origen de blob de Azure, arrastre y coloque el **origen de blob de Azure** en el diseñador de flujos de datos y haga doble clic en él para abrir el editor.</span><span class="sxs-lookup"><span data-stu-id="7476c-105">To see the editor for the Azure Blob Source, drag and drop **Azure Blob Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
1.  <span data-ttu-id="7476c-106">En el campo **Azure storage connection manager** (Administrador de conexiones de Azure Storage), especifique un administrador de conexiones de Azure Storage existente o cree uno nuevo que haga referencia a una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="7476c-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="7476c-107">En el campo **Nombre de contenedor de blobs** , especifique el nombre del contenedor de blobs que contiene los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="7476c-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="7476c-108">En el campo **Nombre de blob** , especifique la ruta de acceso al blob.</span><span class="sxs-lookup"><span data-stu-id="7476c-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="7476c-109">En el campo **Blob file format** (Formato de archivo de blob), especifique el formato de blob que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="7476c-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="7476c-110">Si el formato de archivo es CSV, debe especificar el valor **Column delimiter character** (Carácter delimitador de columna).</span><span class="sxs-lookup"><span data-stu-id="7476c-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="7476c-111">Seleccione también **Nombres de columna de la primera fila de datos** si la primera fila del archivo contiene nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="7476c-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="7476c-112">Después de especificar la información de conexión, cambie a la página **Columnas** para asignar columnas de origen a columnas de destino para el flujo de datos SSIS.</span><span class="sxs-lookup"><span data-stu-id="7476c-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
