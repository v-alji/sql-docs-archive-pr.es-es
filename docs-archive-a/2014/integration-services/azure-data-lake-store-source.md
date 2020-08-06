---
title: Origen de Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSSRC.F1
- SQL11.DTS.DESIGNER.AFPADLSSRC.F1
ms.assetid: 7d9e8457-62aa-4aea-98ee-7d1121dfae4f
author: yualan
ms.author: chugu
ms.openlocfilehash: e5bce25e303b055d734da6a00c73851f4eb0d7ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674287"
---
# <a name="azure-data-lake-store-source"></a><span data-ttu-id="f37e8-102">Origen de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="f37e8-102">Azure Data Lake Store Source</span></span>
  <span data-ttu-id="f37e8-103">El componente **Origen de Azure Data Lake Store** permite que un paquete SSIS lea datos de un Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="f37e8-103">The **Azure Data Lake Store Source** component enables an SSIS package to read data from an Azure Data Lake Store.</span></span> <span data-ttu-id="f37e8-104">Los formatos de archivo admitidos son: Text y Avro.</span><span class="sxs-lookup"><span data-stu-id="f37e8-104">The supported file formats are: Text and Avro.</span></span>
  
## <a name="configure-the-azure-data-lake-store-source"></a><span data-ttu-id="f37e8-105">Configurar Origen de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="f37e8-105">Configure the Azure Data Lake Store Source</span></span> 
  
1.  <span data-ttu-id="f37e8-106">Para ver el editor del origen de Origen de Azure Data Lake Store, arrastre y coloque **Origen de Azure Data Lake Store** en el diseñador de flujos de datos y haga doble clic en él para abrir el editor.</span><span class="sxs-lookup"><span data-stu-id="f37e8-106">To see the editor for the Azure Data Lake Store Source, drag and drop **Azure Data Lake Store Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
2.  <span data-ttu-id="f37e8-107">En el campo **Administrador de conexiones de Azure Data Lake Store** , especifique un administrador de conexiones de Azure Data Lake Store o cree uno nuevo que haga referencia a un servicio de Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="f37e8-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="f37e8-108">Para el campo **Ruta de acceso del archivo** , especifique la ruta de acceso archivo de origen en Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="f37e8-108">For the **File Path** field, specify the file path of the source file in Azure Data Lake Store.</span></span>   
  
    2.  <span data-ttu-id="f37e8-109">En el campo **Formato de archivo** , especifique el formato del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="f37e8-109">For the **File format** field, specify the file format of the source file.</span></span>  
  
        <span data-ttu-id="f37e8-110">Si el formato de archivo es texto, debe especificar el valor del **carácter delimitador de columna** .</span><span class="sxs-lookup"><span data-stu-id="f37e8-110">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="f37e8-111">Seleccione también **Nombres de columna de la primera fila de datos** si la primera fila del archivo contiene nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="f37e8-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
3.  <span data-ttu-id="f37e8-112">Después de especificar la información de conexión, cambie a la página **Columnas** para asignar columnas de origen a columnas de destino para el flujo de datos SSIS.</span><span class="sxs-lookup"><span data-stu-id="f37e8-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
