---
title: Configurar el tamaño máximo de carga de archivos (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ac516c63-1e79-4ae8-bca6-32d3c1a09c00
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34a0adb2f22915289cccfa1f21c51038263acca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743647"
---
# <a name="configure-maximum-file-upload-size-powerpivot-for-sharepoint"></a><span data-ttu-id="952a5-102">Configurar el tamaño de carga máximo de archivos (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="952a5-102">Configure Maximum File Upload Size (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="952a5-103">Los libros PowerPivot contienen grandes cantidades de datos que resultan en archivos que superan el tamaño de archivo máximo permitido en las cargas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="952a5-103">PowerPivot workbooks often contain large amounts of data that result in files that exceed the maximum file size allowed for SharePoint uploads.</span></span> <span data-ttu-id="952a5-104">Al intentar cargar un archivo que supera el límite superior, obtendrá el siguiente error en SharePoint:</span><span class="sxs-lookup"><span data-stu-id="952a5-104">When you try to upload a file that exceeds the upper limit, you will get the following error on SharePoint:</span></span>  
  
-   <span data-ttu-id="952a5-105">“El archivo especificado es mayor que el tamaño de archivo máximo admitido.”</span><span class="sxs-lookup"><span data-stu-id="952a5-105">"The specified file is larger than the maximum supported file size."</span></span>  
  
 <span data-ttu-id="952a5-106">Para aumentar el tamaño de archivo, empiece por ajustar el tamaño máximo del libro de Servicios de Excel en 50 megabytes.</span><span class="sxs-lookup"><span data-stu-id="952a5-106">To increase the file size, start by adjusting the Maximum Workbook Size for Excel Services to 50 megabytes.</span></span> <span data-ttu-id="952a5-107">De esta forma, alinea los límites de tamaño de archivo máximos para Excel a los de las aplicaciones web de SharePoint (establecidos en 50 megabytes de forma predeterminada en SharePoint 2010 y en 200 en SharePoint 2013).</span><span class="sxs-lookup"><span data-stu-id="952a5-107">This aligns the maximum file size limits for Excel to those of SharePoint web applications (set to 50 megabytes by default in SharePoint 2010 and 200 in SharePoint 2013).</span></span> <span data-ttu-id="952a5-108">Si los archivos superan 50 megabytes de tamaño, aumente los límites de tamaño de archivo para Servicios de Excel y la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="952a5-108">If your files exceed 50 megabytes in size, increase the file size limits for both Excel Services and your web application.</span></span>  
  
 <span data-ttu-id="952a5-109">Debe ser administrador de SharePoint para cambiar el tamaño máximo de la carga de archivo.</span><span class="sxs-lookup"><span data-stu-id="952a5-109">You must be a SharePoint administrator to change the maximum file upload size.</span></span>  
  
### <a name="configure-maximum-file-size-for-excel-services"></a><span data-ttu-id="952a5-110">Configurar el tamaño de archivo máximo para Servicios de Excel</span><span class="sxs-lookup"><span data-stu-id="952a5-110">Configure maximum file size for Excel Services</span></span>  
  
1.  <span data-ttu-id="952a5-111">En Administración central, en Administración de aplicaciones, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="952a5-111">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="952a5-112">Haga clic en el nombre de la aplicación de Excel Services.</span><span class="sxs-lookup"><span data-stu-id="952a5-112">Click the name of your Excel Services Application.</span></span>  
  
3.  <span data-ttu-id="952a5-113">Haga clic en **Ubicaciones de archivos de confianza**.</span><span class="sxs-lookup"><span data-stu-id="952a5-113">Click **Trusted File Locations**.</span></span>  
  
4.  <span data-ttu-id="952a5-114">Haga clic en la ubicación para modificar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="952a5-114">Click the location to edit the properties.</span></span> <span data-ttu-id="952a5-115">De forma predeterminada, Servicios de Excel considera la aplicación web predeterminada un sitio de confianza.</span><span class="sxs-lookup"><span data-stu-id="952a5-115">By default, Excel Services considers the default web application a trusted site.</span></span> <span data-ttu-id="952a5-116">Si usa la aplicación web predeterminada, haga clic en **http://** para abrir la página de configuración de esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="952a5-116">If you are using the default web application, click **http://** to open the configuration page for this location.</span></span>  
  
5.  <span data-ttu-id="952a5-117">Desplácese a **Propiedades del libro**.</span><span class="sxs-lookup"><span data-stu-id="952a5-117">Scroll to **Workbook Properties**.</span></span>  
  
6.  <span data-ttu-id="952a5-118">En Tamaño máximo del libro, aumente el tamaño de archivo de 10 (el valor predeterminado) a 50 o un tamaño mayor que contenga los archivos con los que trabajan.</span><span class="sxs-lookup"><span data-stu-id="952a5-118">In Maximum Workbook Size, increase the file size from 10 (the default value) to 50 or a larger size that accommodates the files you are working with.</span></span>  
  
     <span data-ttu-id="952a5-119">De forma predeterminada, 50 megabytes es el tamaño máximo de carga de archivo para las aplicaciones web de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="952a5-119">By default, 50 megabytes is the maximum file upload size for SharePoint web applications.</span></span> <span data-ttu-id="952a5-120">Si establece Tamaño máximo de archivo en un número mayor de 50 megabytes, siga los pasos del procedimiento siguiente para aumentar el valor de Tamaño máximo de carga de la aplicación web de SharePoint al mismo valor.</span><span class="sxs-lookup"><span data-stu-id="952a5-120">If you set Maximum Workbook Size to a number larger than 50 megabytes, follow the steps in the next procedure to increase the Maximum Upload Size for your SharePoint web application to the same value.</span></span>  
  
     <span data-ttu-id="952a5-121">El valor máximo que puede especificar es 2 gigabytes (o 2047 megabytes como se especifica en Administración central).</span><span class="sxs-lookup"><span data-stu-id="952a5-121">The maximum value that you can specify is 2 gigabytes (or 2047 megabytes as specified in Central Administration).</span></span>  
  
7.  <span data-ttu-id="952a5-122">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="952a5-122">Click **OK**.</span></span>  
  
### <a name="configure-maximum-file-size-for-a-sharepoint-web-application"></a><span data-ttu-id="952a5-123">Configurar el tamaño máximo de archivo para una aplicación web de SharePoint</span><span class="sxs-lookup"><span data-stu-id="952a5-123">Configure maximum file size for a SharePoint web application</span></span>  
  
1.  <span data-ttu-id="952a5-124">En administración central, en administración de aplicaciones, haga clic en **Administrar aplicaciones web**.</span><span class="sxs-lookup"><span data-stu-id="952a5-124">In Central Administration, in Application Management, click **Manage web applications**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="952a5-125">Siga estos pasos únicamente si aumentó el valor de Tamaño máximo del libro en Servicios de Excel.</span><span class="sxs-lookup"><span data-stu-id="952a5-125">Perform the following steps only if you increased the Maximum Workbook Size in Excel Services.</span></span>  
  
2.  <span data-ttu-id="952a5-126">Seleccione la aplicación (por ejemplo, **SharePoint - 80**).</span><span class="sxs-lookup"><span data-stu-id="952a5-126">Select the application (for example, **SharePoint - 80**).</span></span>  
  
3.  <span data-ttu-id="952a5-127">En la cinta de Aplicaciones web, haga clic en la flecha abajo en el botón Configuración general.</span><span class="sxs-lookup"><span data-stu-id="952a5-127">On the Web Applications ribbon, click the down arrow on the General Settings button.</span></span>  
  
4.  <span data-ttu-id="952a5-128">Haga clic en **Configuración general**.</span><span class="sxs-lookup"><span data-stu-id="952a5-128">Click **General Settings**.</span></span>  
  
5.  <span data-ttu-id="952a5-129">Desplácese a **Tamaño máximo de carga**.</span><span class="sxs-lookup"><span data-stu-id="952a5-129">Scroll to **Maximum Upload Size**.</span></span>  
  
6.  <span data-ttu-id="952a5-130">Establezca la propiedad en el mismo número o uno mayor que el Tamaño máximo del libro de Excel Services.</span><span class="sxs-lookup"><span data-stu-id="952a5-130">Set the property to the same number, or larger as the Maximum Workbook Size in Excel Services.</span></span>  
  
7.  <span data-ttu-id="952a5-131">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="952a5-131">Click **OK**.</span></span>  
  
  
