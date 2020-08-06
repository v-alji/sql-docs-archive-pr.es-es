---
title: Destino de blob de Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdest.f1
- sql11.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb406d38b17748e8284acee4b2849a9fd99e53ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748848"
---
# <a name="azure-blob-destination"></a><span data-ttu-id="39dce-102">Destino de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="39dce-102">Azure Blob Destination</span></span>
  <span data-ttu-id="39dce-103">El componente **Azure Blob Destination** (Destino de blobs de Azure) permite que un paquete SSIS escriba datos en un blob de Azure.</span><span class="sxs-lookup"><span data-stu-id="39dce-103">The **Azure Blob Destination** component enables an SSIS package to write data to an Azure blob.</span></span> <span data-ttu-id="39dce-104">Los formatos de archivo admitidos son: CSV y AVRO.</span><span class="sxs-lookup"><span data-stu-id="39dce-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="39dce-105">Arrastre: Quite el **destino de BLOB de Azure** al diseñador de flujo de datos y haga doble clic en él para ver el editor).</span><span class="sxs-lookup"><span data-stu-id="39dce-105">Ddrag-drop **Azure Blob Destination** to the data flow designer and double-click it to see the editor).</span></span>  
  
1.  <span data-ttu-id="39dce-106">En el campo **Azure storage connection manager** (Administrador de conexiones de Azure Storage), especifique un administrador de conexiones de Azure Storage existente o cree uno nuevo que haga referencia a una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="39dce-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="39dce-107">En el campo **Nombre de contenedor de blobs** , especifique el nombre del contenedor de blobs que contiene los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="39dce-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="39dce-108">En el campo **Nombre de blob** , especifique la ruta de acceso al blob.</span><span class="sxs-lookup"><span data-stu-id="39dce-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="39dce-109">En el campo **Blob file format** (Formato de archivo de blob), especifique el formato de blob que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="39dce-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="39dce-110">Si el formato de archivo es CSV, debe especificar el valor **Column delimiter character** (Carácter delimitador de columna).</span><span class="sxs-lookup"><span data-stu-id="39dce-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="39dce-111">Seleccione también **nombres de columna en la primera fila de datos** si la primera fila del archivo contiene nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="39dce-111">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="39dce-112">Después de especificar la información de conexión, cambie a la página **Columnas** para asignar columnas de origen a columnas de destino para el flujo de datos SSIS.</span><span class="sxs-lookup"><span data-stu-id="39dce-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
