---
title: Conectarse a un archivo de Microsoft Excel (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670015"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a><span data-ttu-id="0d2b9-102">Conectar con un archivo de Microsoft Excel (SSAS)</span><span class="sxs-lookup"><span data-stu-id="0d2b9-102">Connect to a Microsoft Excel File (SSAS)</span></span>
  <span data-ttu-id="0d2b9-103">Esta página del **Asistente para la importación de tablas** le permite conectar con un archivo de Microsoft Excel almacenado en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-103">This page of the **Table Import Wizard** enables you to connect to a Microsoft Excel file stored on the local machine.</span></span> <span data-ttu-id="0d2b9-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="0d2b9-105">Para conectarse a un archivo de Microsoft Excel, debe tener instalado en el equipo el proveedor ACE adecuado.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-105">To connect to a Microsoft Excel file, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="0d2b9-106">Para más información, vea [Orígenes de datos compatibles &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0d2b9-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d2b9-107">Las credenciales del usuario actual se utilizan al seleccionar un archivo en esta página.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="0d2b9-108">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer el archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0d2b9-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0d2b9-109">UI element list</span></span>  
 <span data-ttu-id="0d2b9-110">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="0d2b9-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="0d2b9-111">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="0d2b9-112">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-112">This is a required field.</span></span>  
  
 <span data-ttu-id="0d2b9-113">**Ruta de acceso del archivo de Excel**</span><span class="sxs-lookup"><span data-stu-id="0d2b9-113">**Excel File Path**</span></span>  
 <span data-ttu-id="0d2b9-114">Especifique la ruta de acceso completa para el archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-114">Specify a full path for the Excel file.</span></span>  
  
 <span data-ttu-id="0d2b9-115">**Browse**</span><span class="sxs-lookup"><span data-stu-id="0d2b9-115">**Browse**</span></span>  
 <span data-ttu-id="0d2b9-116">Navegue a una ubicación donde haya un archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-116">Navigate to a location where an Excel file is available.</span></span>  
  
 <span data-ttu-id="0d2b9-117">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="0d2b9-117">**Advanced**</span></span>  
 <span data-ttu-id="0d2b9-118">Establezca las propiedades de conexión adicionales mediante el cuadro de diálogo **establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="0d2b9-118">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="0d2b9-119">**Usar primera fila como encabezados de columna**</span><span class="sxs-lookup"><span data-stu-id="0d2b9-119">**Use first row as column headers**</span></span>  
 <span data-ttu-id="0d2b9-120">Especifique si utilizar la primera fila de datos como encabezados de columna de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-120">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="0d2b9-121">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="0d2b9-121">**Test Connection**</span></span>  
 <span data-ttu-id="0d2b9-122">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-122">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="0d2b9-123">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="0d2b9-123">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
