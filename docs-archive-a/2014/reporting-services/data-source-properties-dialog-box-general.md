---
title: Propiedades del origen de datos (cuadro de diálogo), general | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.general.f1
- "10120"
ms.assetid: 44b5edd3-5c11-4d3d-91b8-5871aa0572ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c79ad70cdd4dcb10e1abce1102fa39eef4c67461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662667"
---
# <a name="data-source-properties-dialog-box-general"></a><span data-ttu-id="1870b-102">Propiedades del origen de datos (cuadro de diálogo), General</span><span class="sxs-lookup"><span data-stu-id="1870b-102">Data Source Properties Dialog Box, General</span></span>
  <span data-ttu-id="1870b-103">Seleccione **General** en el cuadro de diálogo **Propiedades del origen de datos** para mostrar y modificar la información de conexión de un origen de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="1870b-103">Select **General** on the **Data Source Properties** dialog box to display and modify connection information for a data source in the report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1870b-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="1870b-104">Options</span></span>  
 <span data-ttu-id="1870b-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1870b-105">**Name**</span></span>  
 <span data-ttu-id="1870b-106">Escriba el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1870b-106">Type the name of the data source.</span></span> <span data-ttu-id="1870b-107">Dicho nombre debe ser único en el informe.</span><span class="sxs-lookup"><span data-stu-id="1870b-107">The data source name must be unique within the report.</span></span> <span data-ttu-id="1870b-108">De forma predeterminada, al origen de datos se le asigna un nombre general, como DataSource1 o DataSource2.</span><span class="sxs-lookup"><span data-stu-id="1870b-108">By default, a general name, such as DataSource1 or DataSource2, is assigned to the data source.</span></span>  
  
 <span data-ttu-id="1870b-109">**Conexión incrustada**</span><span class="sxs-lookup"><span data-stu-id="1870b-109">**Embedded connection**</span></span>  
 <span data-ttu-id="1870b-110">Seleccione esta opción si no desea utilizar un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="1870b-110">Select this option when you do not want to use a shared data source.</span></span>  
  
 <span data-ttu-id="1870b-111">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1870b-111">**Type**</span></span>  
 <span data-ttu-id="1870b-112">Seleccione una extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="1870b-112">Select a data processing extension.</span></span> <span data-ttu-id="1870b-113">En la lista se muestran todas las extensiones registradas.</span><span class="sxs-lookup"><span data-stu-id="1870b-113">The list displays all registered extensions.</span></span>  
  
 <span data-ttu-id="1870b-114">**Cadena de conexión**</span><span class="sxs-lookup"><span data-stu-id="1870b-114">**Connection string**</span></span>  
 <span data-ttu-id="1870b-115">Escriba una cadena de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1870b-115">Enter a connection string for the data source.</span></span> <span data-ttu-id="1870b-116">Haga clic en **Editar** para generar la cadena de conexión mediante el cuadro de diálogo **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="1870b-116">Click **Edit** to build the connection string using the **Connection Properties** dialog box.</span></span> <span data-ttu-id="1870b-117">Haga clic en el botón **Expresiones** (*fx*) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="1870b-117">Click the **Expressions** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="1870b-118">**Utilizar referencia de origen de datos compartido**</span><span class="sxs-lookup"><span data-stu-id="1870b-118">**Use shared data source reference**</span></span>  
 <span data-ttu-id="1870b-119">Seleccione esta opción para establecer un vínculo con un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="1870b-119">Select this option to link to a shared data source.</span></span> <span data-ttu-id="1870b-120">Seleccione un origen de datos compartido en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1870b-120">Select a shared data source from the drop-down list.</span></span> <span data-ttu-id="1870b-121">Para editar el origen de datos seleccionado, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1870b-121">To edit the selected data source, click **Edit**.</span></span> <span data-ttu-id="1870b-122">Si se selecciona **Utilizar referencia de origen de datos compartido** , **Tipo** y **Cadena de conexión** se deshabilitan.</span><span class="sxs-lookup"><span data-stu-id="1870b-122">If **Use shared data source reference** is selected, **Type** and **Connection string** are disabled.</span></span>  
  
 <span data-ttu-id="1870b-123">**Usar una sola transacción al procesar las consultas**</span><span class="sxs-lookup"><span data-stu-id="1870b-123">**Use a single transaction when processing the queries**</span></span>  
 <span data-ttu-id="1870b-124">Seleccione esta opción para indicar que los conjuntos de datos que usan este origen de datos deben ejecutarse en una sola transacción en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1870b-124">Select this option to indicate that datasets that use this data source are run in a single transaction against the database.</span></span> <span data-ttu-id="1870b-125">Para incluir transacciones para subinformes que usan el mismo origen de datos, establezca **MergeTransactions** en **True** en la sección de propiedades **Otros** del panel **Propiedades** del subinforme.</span><span class="sxs-lookup"><span data-stu-id="1870b-125">To include transactions for subreports that use the same data source, set **MergeTransactions** to **True** in the subreport's **Other** properties section of the **Properties** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1870b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1870b-126">See Also</span></span>  
 <span data-ttu-id="1870b-127">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1870b-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="1870b-128">[Crear un origen de datos incrustado o compartido &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1870b-128">[Create an Embedded or Shared Data Source &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span></span>  
 <span data-ttu-id="1870b-129">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1870b-129">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="1870b-130">Propiedades del origen de datos (cuadro de diálogo), Credenciales</span><span class="sxs-lookup"><span data-stu-id="1870b-130">Data Source Properties Dialog Box, Credentials</span></span>](../../2014/reporting-services/data-source-properties-dialog-box-credentials.md)  
  
  
