---
title: Revisar y generar scripts de registro complementario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671131"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a><span data-ttu-id="092ec-102">Revisar y generar scripts de registro complementario</span><span class="sxs-lookup"><span data-stu-id="092ec-102">Review and Generate Supplemental Logging Scripts</span></span>
  <span data-ttu-id="092ec-103">Use la pestaña **Scripts** para ejecutar o volver a ejecutar un script en la base de datos de origen de Oracle que configura el registro complementario.</span><span class="sxs-lookup"><span data-stu-id="092ec-103">Use the **Scripts** tab to run or re-run a script on the Oracle source database that sets up supplemental logging.</span></span>  
  
 <span data-ttu-id="092ec-104">Antes de ejecutar los scripts, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="092ec-104">Before you run the scripts select one of the following:</span></span>  
  
 <span data-ttu-id="092ec-105">**Incluir cambios en esta sesión**</span><span class="sxs-lookup"><span data-stu-id="092ec-105">**Include changes in this session**</span></span>  
 <span data-ttu-id="092ec-106">Seleccione esta opción para ejecutar el script en cualquier tabla nueva que se agregó a la instancia CDC o en tablas que se modificaron de cualquier forma mediante el editor de propiedades.</span><span class="sxs-lookup"><span data-stu-id="092ec-106">Select this to run the script on any new table that was added to the CDC instance or on tables that were changed in any way using the Properties editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="092ec-107">Si no se ha realizado ningún cambio en las tablas de la instancia CDC, el área de script de registro complementario de Oracle estará vacío.</span><span class="sxs-lookup"><span data-stu-id="092ec-107">If no changes were made to the tables in the CDC instance, the Oracle supplemental logging script area will be empty.</span></span>  
  
 <span data-ttu-id="092ec-108">**Incluir todas las tablas e instancias de captura**</span><span class="sxs-lookup"><span data-stu-id="092ec-108">**Include all tables/capture instances**</span></span>  
 <span data-ttu-id="092ec-109">Seleccione esta opción para ejecutar el script en todas las tablas e instancias de captura de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="092ec-109">Select this to run the script on all of the tables and capture instances in the CDC instance.</span></span>  
  
 <span data-ttu-id="092ec-110">Después de seleccionar una de estas opciones, ejecute el script de registro complementario.</span><span class="sxs-lookup"><span data-stu-id="092ec-110">After you select one of these options, run the supplemental logging script.</span></span>  
  
### <a name="to-run-the-supplemental-logging-scripts"></a><span data-ttu-id="092ec-111">Para ejecutar los scripts de registro complementario</span><span class="sxs-lookup"><span data-stu-id="092ec-111">To run the supplemental logging scripts</span></span>  
  
1.  <span data-ttu-id="092ec-112">Haga clic en **Ejecutar script** para ejecutar el script de registro complementario en las tablas definidas para la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="092ec-112">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="092ec-113">Este script indica a la base de datos de Oracle que escriba todas las columnas de interés en sus registros de transacciones al registrar operaciones UPDATE en tablas capturadas.</span><span class="sxs-lookup"><span data-stu-id="092ec-113">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="092ec-114">Normalmente es un administrador del sistema de Oracle quien examina y ejecuta este script.</span><span class="sxs-lookup"><span data-stu-id="092ec-114">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
2.  <span data-ttu-id="092ec-115">Al ejecutar los scripts de registro complementario, se abre el cuadro de diálogo Credenciales de Oracle para ejecutar script donde debe proporcionar un nombre de usuario y una contraseña válidos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="092ec-115">When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="092ec-116">Para obtener información acerca de cómo proporcionar las credenciales adecuadas de Oracle, vea [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="092ec-116">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
 <span data-ttu-id="092ec-117">También puede ejecutar los scripts manualmente mediante SQL \* Plus, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="092ec-117">You can also run the scripts manually using SQL \* Plus, if necessary.</span></span>  
  
### <a name="to-run-the-scripts-manually"></a><span data-ttu-id="092ec-118">Para ejecutar los scripts manualmente</span><span class="sxs-lookup"><span data-stu-id="092ec-118">To run the scripts manually</span></span>  
  
1.  <span data-ttu-id="092ec-119">Haga clic en **Copiar** para pegar el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="092ec-119">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="092ec-120">Abra SQL\* Plus y vaya al directorio donde se encuentra la base de datos de origen de Oracle.</span><span class="sxs-lookup"><span data-stu-id="092ec-120">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="092ec-121">Pegue el script en SQL\*Plus para ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="092ec-121">Paste the script into SQL\*Plus to run it.</span></span>  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a><span data-ttu-id="092ec-122">Para guardar el script de registro complementario en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="092ec-122">To save the supplemental logging script in a text file</span></span>  
  
1.  <span data-ttu-id="092ec-123">Haga clic en **Guardar como** y vaya hasta la ubicación donde desee guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="092ec-123">Click **Save as** and browse to the location where you want to save the file.</span></span>  
  
2.  <span data-ttu-id="092ec-124">Asigne un nombre al archivo y haga clic en **Guardar** para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="092ec-124">Give the file a name and click **Save** to save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="092ec-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="092ec-125">See Also</span></span>  
 <span data-ttu-id="092ec-126">[Cómo editar las propiedades de la instancia CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="092ec-126">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="092ec-127">Credenciales de Oracle para ejecutar script</span><span class="sxs-lookup"><span data-stu-id="092ec-127">Oracle Credentials for Running Script</span></span>](oracle-credentials-for-running-script.md)  
  
  
