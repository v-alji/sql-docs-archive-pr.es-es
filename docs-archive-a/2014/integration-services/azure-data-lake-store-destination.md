---
title: Destino de Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSDEST.F1
- SQL11.DTS.DESIGNER.AFPADLSDEST.F1
ms.assetid: d0e86032-2a6b-48b2-898f-e94328474fde
author: yualan
ms.author: chugu
ms.openlocfilehash: 14248d14b6a944250c33a19c8cf83ab0e0330587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749406"
---
# <a name="azure-data-lake-store-destination"></a><span data-ttu-id="360c7-102">Destino de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="360c7-102">Azure Data Lake Store Destination</span></span>
  <span data-ttu-id="360c7-103">El componente **Destino de Azure Data Lake Store** permite que un paquete SSIS escriba datos en un Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="360c7-103">The **Azure Data Lake Store Destination** component enables an SSIS package to write data to an Azure Data Lake Store.</span></span> <span data-ttu-id="360c7-104">Los formatos de archivo admitidos son: Text, Avro y ORC.</span><span class="sxs-lookup"><span data-stu-id="360c7-104">The supported file formats are: Text, Avro and ORC.</span></span> 
  
## <a name="configure-the-azure-data-lake-store-destination"></a><span data-ttu-id="360c7-105">Configurar Destino de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="360c7-105">Configure the Azure Data Lake Store Destination</span></span> 

1. <span data-ttu-id="360c7-106">Arrastre y coloque **Destino de Azure Data Lake Store** en el diseñador de flujos de datos y haga doble clic en él para ver el editor.</span><span class="sxs-lookup"><span data-stu-id="360c7-106">Drag-drop **Azure Data Lake Store Destination** to the data flow designer and double-click it to see the editor.</span></span>  

2.  <span data-ttu-id="360c7-107">En el campo **Administrador de conexiones de Azure Data Lake Store** , especifique un administrador de conexiones de Azure Data Lake Store o cree uno nuevo que haga referencia a un servicio de Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="360c7-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="360c7-108">En el campo **Ruta de acceso del archivo** , especifique el nombre de archivo en el que quiere escribir datos.</span><span class="sxs-lookup"><span data-stu-id="360c7-108">For the **File Path** field, specify the file name you want to write data to.</span></span> <span data-ttu-id="360c7-109">Si el archivo ya existe, se sobrescribirá su contenido.</span><span class="sxs-lookup"><span data-stu-id="360c7-109">If this file already exist, its content will be overwritten.</span></span>  
  
    2.  <span data-ttu-id="360c7-110">En el campo **Formato de archivo** , especifique el formato que quiere utilizar.</span><span class="sxs-lookup"><span data-stu-id="360c7-110">For the **File format** field, specify the file format you want to use.</span></span>  
  
        <span data-ttu-id="360c7-111">Si el formato de archivo es texto, debe especificar el valor del **carácter delimitador de columna** .</span><span class="sxs-lookup"><span data-stu-id="360c7-111">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="360c7-112">Seleccione también **nombres de columna en la primera fila de datos** si la primera fila del archivo contiene nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="360c7-112">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  

        <span data-ttu-id="360c7-113">Si el formato de archivo es ORC, debe instalar JRE de la plataforma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="360c7-113">If the file format is ORC, you need to install JRE of corresponding platform.</span></span> 
  
3.  <span data-ttu-id="360c7-114">Después de especificar la información de conexión, cambie a la página **Columnas** para asignar columnas de origen a columnas de destino para el flujo de datos SSIS.</span><span class="sxs-lookup"><span data-stu-id="360c7-114">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
