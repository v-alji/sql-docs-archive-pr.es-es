---
title: Script de implementación de instancia CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6deea884168c2329e312eeaa2be16c28a955cca3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750097"
---
# <a name="cdc-instance-deployment-script"></a><span data-ttu-id="47024-102">Script de implementación de instancia CDC</span><span class="sxs-lookup"><span data-stu-id="47024-102">CDC Instance Deployment Script</span></span>
  <span data-ttu-id="47024-103">El cuadro de diálogo Script de implementación de instancia CDC muestra el script de implementación de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="47024-103">The CDC Instance Deployment Script dialog box that displays the CDC instance deployment script.</span></span> <span data-ttu-id="47024-104">Este script se puede usar para volver a crear la base de datos CDC con todos sus artefactos en otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferente.</span><span class="sxs-lookup"><span data-stu-id="47024-104">This script can be used to re-create the CDC database with all of its artifacts on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="47024-105">Al completarse el script de implementación, debe asegurarse de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47024-105">At the completion of the deployment script, you should make sure of the following:</span></span>  
  
-   <span data-ttu-id="47024-106">El script de implementación da por supuesto que la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino se preparó para CDC de Oracle mediante la Consola de configuración del servicio CDC de Oracle o mediante el **script de preparación** que el programa crea.</span><span class="sxs-lookup"><span data-stu-id="47024-106">The deployment script assumes that the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance was prepared for Oracle CDC, by using the Oracle CDC Service Configuration Console or by using **prepare script** that program creates.</span></span>  
  
-   <span data-ttu-id="47024-107">La parte del script que se emplea para habilitar la base de datos para CDC debe ejecutarla un `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="47024-107">The part of the script that is used to enable the database for CDC needs to be run by a `sysadmin`.</span></span>  
  
-   <span data-ttu-id="47024-108">El script no conserva la contraseña de minería de registros de Oracle.</span><span class="sxs-lookup"><span data-stu-id="47024-108">The script does not preserve the Oracle log-mining password.</span></span> <span data-ttu-id="47024-109">Es necesario establecerla manualmente después de que se ejecute el script y se inicie el servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="47024-109">This needs to be set manually after the script is run and the Oracle CDC Service is started.</span></span>  
  
 <span data-ttu-id="47024-110">Seleccione las opciones siguientes en el cuadro de diálogo **Script de implementación de instancia CDC** .</span><span class="sxs-lookup"><span data-stu-id="47024-110">Select the following options in the **CDC Instance Deployment Script** dialog box.</span></span>  
  
 <span data-ttu-id="47024-111">**Guardar como**</span><span class="sxs-lookup"><span data-stu-id="47024-111">**Save As**</span></span>  
 <span data-ttu-id="47024-112">Guarda el script en un archivo de texto que puede guardar en cualquier ubicación que desee.</span><span class="sxs-lookup"><span data-stu-id="47024-112">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="47024-113">Puede copiar el archivo con el script a cualquier otro servidor para ejecutarlo en él.</span><span class="sxs-lookup"><span data-stu-id="47024-113">You can copy the file with the script to any other server to run it there.</span></span>  
  
 <span data-ttu-id="47024-114">**Copy**</span><span class="sxs-lookup"><span data-stu-id="47024-114">**Copy**</span></span>  
 <span data-ttu-id="47024-115">Copia el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="47024-115">Copies the script to the clipboard.</span></span> <span data-ttu-id="47024-116">Puede pegar el script en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o en cualquier editor de texto para ejecutar los scripts posteriormente.</span><span class="sxs-lookup"><span data-stu-id="47024-116">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor to run the scripts later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47024-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47024-117">See Also</span></span>  
 [<span data-ttu-id="47024-118">Preparar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="47024-118">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
