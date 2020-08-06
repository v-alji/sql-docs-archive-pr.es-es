---
title: Generar y ejecutar el script de registro complementario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- supLog
ms.assetid: 6e940d93-12c6-4cda-9333-5489b245f0e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1437a4b0f790376268095d8e52afa981af865b44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744272"
---
# <a name="generate-and-run-the-supplemental-logging-script"></a><span data-ttu-id="56ba2-102">Generar y ejecutar el script de registro complementario</span><span class="sxs-lookup"><span data-stu-id="56ba2-102">Generate and Run the Supplemental Logging Script</span></span>
  <span data-ttu-id="56ba2-103">Use la página Configurar tablas para capturar cambios con el fin de ejecutar un script en la base de datos de origen de Oracle que configurará el registro complementario.</span><span class="sxs-lookup"><span data-stu-id="56ba2-103">Use the Set up Tables for Capturing Changes page to run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
 <span data-ttu-id="56ba2-104">**Para ejecutar los scripts de registro complementario**</span><span class="sxs-lookup"><span data-stu-id="56ba2-104">**To run the supplemental logging scripts**</span></span>  
  
 <span data-ttu-id="56ba2-105">Haga clic en **Ejecutar script** para ejecutar el script de registro complementario en las tablas definidas para la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="56ba2-105">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="56ba2-106">Este script indica a la base de datos de Oracle que escriba todas las columnas de interés en sus registros de transacciones al registrar operaciones UPDATE en tablas capturadas.</span><span class="sxs-lookup"><span data-stu-id="56ba2-106">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="56ba2-107">Normalmente es un administrador del sistema de Oracle quien examina y ejecuta este script.</span><span class="sxs-lookup"><span data-stu-id="56ba2-107">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
 <span data-ttu-id="56ba2-108">También puede ejecutar los scripts manualmente mediante SQL \* Plus.</span><span class="sxs-lookup"><span data-stu-id="56ba2-108">You can also run the scripts manually using SQL \* Plus.</span></span>  
  
 <span data-ttu-id="56ba2-109">**Para ejecutar los scripts manualmente**</span><span class="sxs-lookup"><span data-stu-id="56ba2-109">**To run the scripts manually**</span></span>  
  
 <span data-ttu-id="56ba2-110">Haga clic en **Copiar** para pegar el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="56ba2-110">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="56ba2-111">Abra SQL\* Plus y vaya al directorio donde se encuentra la base de datos de origen de Oracle.</span><span class="sxs-lookup"><span data-stu-id="56ba2-111">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="56ba2-112">Pegue el script en SQL\*Plus para ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="56ba2-112">Paste the script into SQL\*Plus to run it.</span></span>  
  
 <span data-ttu-id="56ba2-113">Para guardar el script de registro complementario en un archivo de texto, haga clic en **Guardar como** y vaya hasta la ubicación donde desee guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="56ba2-113">To save the supplemental logging script in a text file, click **Save as** and browse to the location where you want to save the file.</span></span> <span data-ttu-id="56ba2-114">Asigne un nombre al archivo y haga clic en **Guardar** para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="56ba2-114">Give the file a name and click **Save** to save the file.</span></span>  
  
 <span data-ttu-id="56ba2-115">Haga clic en **Siguiente** para [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span><span class="sxs-lookup"><span data-stu-id="56ba2-115">Click **Next** to [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ba2-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56ba2-116">See Also</span></span>  
 <span data-ttu-id="56ba2-117">[Cómo crear la instancia de base de datos de cambios de SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="56ba2-117">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="56ba2-118">Revisar y generar Scripts de registro complementario</span><span class="sxs-lookup"><span data-stu-id="56ba2-118">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
