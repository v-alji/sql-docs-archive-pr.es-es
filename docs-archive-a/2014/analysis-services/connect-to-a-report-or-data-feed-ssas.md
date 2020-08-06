---
title: Conectarse a un informe o a una fuente de distribución de datos (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76dd51c32d13e64b0368267ba7ac66aa6d76a784
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670007"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a><span data-ttu-id="14bdc-102">Conectarse a un informe o a una fuente de distribución de datos (SSAS)</span><span class="sxs-lookup"><span data-stu-id="14bdc-102">Connect to a Report or Data Feed (SSAS)</span></span>
  <span data-ttu-id="14bdc-103">Esta página del **Asistente para la importación de tablas** le permite conectar con una fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-103">This page of the **Table Import Wizard** enables you to connect to a data feed.</span></span> <span data-ttu-id="14bdc-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="14bdc-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="from-a-report"></a><span data-ttu-id="14bdc-105">Desde un informe</span><span class="sxs-lookup"><span data-stu-id="14bdc-105">From a Report</span></span>  
 <span data-ttu-id="14bdc-106">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="14bdc-106">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="14bdc-107">Escriba un nombre descriptivo para la conexión con la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-107">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="14bdc-108">**Ruta de acceso del informe**</span><span class="sxs-lookup"><span data-stu-id="14bdc-108">**Report Path**</span></span>  
 <span data-ttu-id="14bdc-109">Enumera la dirección URL de un informe de SQL Server Reporting Services que genera fuentes de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-109">Lists the URL for a SQL Server Reporting Services report that generates data feeds.</span></span> <span data-ttu-id="14bdc-110">Haga clic en **Examinar** para especificar la dirección URL del informe.</span><span class="sxs-lookup"><span data-stu-id="14bdc-110">Click **Browse** to specify the URL for the report.</span></span>  
  
 <span data-ttu-id="14bdc-111">Haga clic en **Ver informe** para mostrar el informe.</span><span class="sxs-lookup"><span data-stu-id="14bdc-111">Click **View Report** to display the report.</span></span>  
  
 <span data-ttu-id="14bdc-112">**Browse**</span><span class="sxs-lookup"><span data-stu-id="14bdc-112">**Browse**</span></span>  
 <span data-ttu-id="14bdc-113">Navegue a una ubicación donde haya un informe.</span><span class="sxs-lookup"><span data-stu-id="14bdc-113">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="14bdc-114">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="14bdc-114">**Advanced**</span></span>  
 <span data-ttu-id="14bdc-115">Establezca las propiedades de conexión adicionales mediante el cuadro de diálogo **establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="14bdc-115">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="14bdc-116">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="14bdc-116">**Test Connection**</span></span>  
 <span data-ttu-id="14bdc-117">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="14bdc-117">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="14bdc-118">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="14bdc-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-an-azure-datamarket-dataset"></a><span data-ttu-id="14bdc-119">De un conjunto de datos de Azure DataMarket</span><span class="sxs-lookup"><span data-stu-id="14bdc-119">From an Azure DataMarket Dataset</span></span>  
 <span data-ttu-id="14bdc-120">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="14bdc-120">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="14bdc-121">Escriba un nombre descriptivo para la conexión con la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-121">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="14bdc-122">**Dirección URL de la fuente de distribución de datos**</span><span class="sxs-lookup"><span data-stu-id="14bdc-122">**Data Feed URL**</span></span>  
 <span data-ttu-id="14bdc-123">Escriba la ruta de acceso completa a un documento de servicio Atom (.atomsvc, .atom) o la dirección URL de una sola fuente de distribución de datos, o bien haga clic en **Examinar** para seleccionar un documento de servicio Atom.</span><span class="sxs-lookup"><span data-stu-id="14bdc-123">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="14bdc-124">**Browse**</span><span class="sxs-lookup"><span data-stu-id="14bdc-124">**Browse**</span></span>  
 <span data-ttu-id="14bdc-125">Navegue a una ubicación donde haya un informe.</span><span class="sxs-lookup"><span data-stu-id="14bdc-125">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="14bdc-126">Haga clic en **Ver conjuntos de datos de Azure DataMarket disponibles** para mostrar los conjuntos de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="14bdc-126">Click **View available Azure DataMarket datasets** to display available datasets.</span></span>  
  
 <span data-ttu-id="14bdc-127">**Clave de cuenta**</span><span class="sxs-lookup"><span data-stu-id="14bdc-127">**Account key**</span></span>  
 <span data-ttu-id="14bdc-128">Especifique la clave de cuenta que se usa para acceder a las suscripciones del conjunto de los conjuntos de Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="14bdc-128">Specify the account key used to access your Azure Marketplace dataset subscriptions.</span></span>  
  
 <span data-ttu-id="14bdc-129">**Localización**</span><span class="sxs-lookup"><span data-stu-id="14bdc-129">**Find**</span></span>  
 <span data-ttu-id="14bdc-130">Busque una clave de cuenta asociada a una cuenta de Windows Live.</span><span class="sxs-lookup"><span data-stu-id="14bdc-130">Locate an account key associated with a Windows Live account.</span></span>  
  
 <span data-ttu-id="14bdc-131">**Guardar mi clave de cuenta**</span><span class="sxs-lookup"><span data-stu-id="14bdc-131">**Save my account key**</span></span>  
 <span data-ttu-id="14bdc-132">Guarda la clave de cuenta (cifrada) con la conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-132">Saves the account key (encrypted) with the data connection.</span></span>  
  
 <span data-ttu-id="14bdc-133">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="14bdc-133">**Advanced**</span></span>  
 <span data-ttu-id="14bdc-134">Establezca las propiedades de conexión adicionales mediante el cuadro de diálogo **establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="14bdc-134">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="14bdc-135">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="14bdc-135">**Test Connection**</span></span>  
 <span data-ttu-id="14bdc-136">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="14bdc-136">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="14bdc-137">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="14bdc-137">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-other-feeds"></a><span data-ttu-id="14bdc-138">De otras fuentes</span><span class="sxs-lookup"><span data-stu-id="14bdc-138">From Other Feeds</span></span>  
 <span data-ttu-id="14bdc-139">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="14bdc-139">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="14bdc-140">Escriba un nombre descriptivo para la conexión con la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-140">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="14bdc-141">**Dirección URL de la fuente de distribución de datos**</span><span class="sxs-lookup"><span data-stu-id="14bdc-141">**Data Feed URL**</span></span>  
 <span data-ttu-id="14bdc-142">Escriba la ruta de acceso completa a un documento de servicio Atom (.atomsvc, .atom) o la dirección URL de una sola fuente de distribución de datos, o bien haga clic en **Examinar** para seleccionar un documento de servicio Atom.</span><span class="sxs-lookup"><span data-stu-id="14bdc-142">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="14bdc-143">Haga clic en **Incluir todas las columnas de fuente** para especificar si se importan todas las columnas de fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-143">Click **Include all feed columns** to specify whether all the data feed columns are imported.</span></span>  
  
 <span data-ttu-id="14bdc-144">**Browse**</span><span class="sxs-lookup"><span data-stu-id="14bdc-144">**Browse**</span></span>  
 <span data-ttu-id="14bdc-145">Navegue hasta una ubicación donde haya una fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="14bdc-145">Navigate to a location where a data feed is available.</span></span>  
  
 <span data-ttu-id="14bdc-146">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="14bdc-146">**Advanced**</span></span>  
 <span data-ttu-id="14bdc-147">Establezca las propiedades de conexión adicionales con el cuadro de diálogo **Establecer propiedades avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="14bdc-147">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="14bdc-148">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="14bdc-148">**Test Connection**</span></span>  
 <span data-ttu-id="14bdc-149">Intente establecer una conexión con el origen de datos usando la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="14bdc-149">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="14bdc-150">Se muestra un mensaje que indica si la conexión es correcta.</span><span class="sxs-lookup"><span data-stu-id="14bdc-150">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
