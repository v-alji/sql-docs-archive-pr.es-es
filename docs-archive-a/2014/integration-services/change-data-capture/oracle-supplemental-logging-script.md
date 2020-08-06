---
title: Script de registro complementario de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e6ee618-b89b-46c7-92ad-4fc5ef7b777a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0aa55e71c17574eba9e25e098a3881b0eb4c9e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744248"
---
# <a name="oracle-supplemental-logging-script"></a><span data-ttu-id="bd9b3-102">Script de registro complementario de Oracle</span><span class="sxs-lookup"><span data-stu-id="bd9b3-102">Oracle Supplemental Logging Script</span></span>
  <span data-ttu-id="bd9b3-103">Este cuadro de diálogo muestra el script de registro complementario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-103">This dialog box shows the script the Oracle supplemental logging script.</span></span>  
  
 <span data-ttu-id="bd9b3-104">Al preparar una instancia CDC para su uso, el diseñador CDC crea un script SQL de Oracle que configura el registro complementario para las tablas que se van a capturar.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-104">When you prepare a CDC Instance for use, the CDC Designer creates an Oracle SQL script that sets up supplemental logging for the tables to be captured.</span></span> <span data-ttu-id="bd9b3-105">El script de registro complementario indica a Oracle que cuando se actualiza una tabla determinada, los registros de cambios que escribe en el registro de transacciones deben contener los datos de todas las columnas de interés, no solo de las columnas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-105">The supplemental logging script tells Oracle that when a specific table is updated, the change records it writes to the transaction log should contain the data of all columns of interest, not just the columns that changed.</span></span>  
  
 <span data-ttu-id="bd9b3-106">Dependiendo de las directivas DBA de Oracle de la organización, la ejecución del script de registro complementario puede necesitar su revisión y aprobación por parte de un administrador de bases de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-106">Depending on the Oracle DBA policies in your organization, running the supplemental logging script may require a review and approval by an Oracle DBA.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bd9b3-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="bd9b3-107">Options</span></span>  
 <span data-ttu-id="bd9b3-108">A continuación se indican las opciones disponibles sobre cómo ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-108">The following are the available options for how to execute the script.</span></span>  
  
 <span data-ttu-id="bd9b3-109">**Ejecutar script**</span><span class="sxs-lookup"><span data-stu-id="bd9b3-109">**Run Script**</span></span>  
 <span data-ttu-id="bd9b3-110">Ejecuta el script de registro complementario en las tablas definidas para la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-110">Runs the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="bd9b3-111">Para ejecutar este script, el usuario de Oracle debe tener el permiso ALTER TABLE para todas las tablas que se van a capturar y el permiso SELECT en la vista DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-111">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span> <span data-ttu-id="bd9b3-112">Además, el usuario de Oracle debe tener las credenciales para usar una base de datos de Oracle con los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-112">In addition, the Oracle user must have the credentials for an Oracle database use with the required permissions.</span></span> <span data-ttu-id="bd9b3-113">Puede permitir que el programa le solicite las credenciales de Oracle y que ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-113">You can let the program prompt you for the Oracle credentials and then have it run the script.</span></span>  
  
 <span data-ttu-id="bd9b3-114">**Guardar como**</span><span class="sxs-lookup"><span data-stu-id="bd9b3-114">**Save As**</span></span>  
 <span data-ttu-id="bd9b3-115">Guarda el script en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-115">Saves the script to a text file.</span></span> <span data-ttu-id="bd9b3-116">Se emplea si un administrador de bases de datos (DBA) de Oracle necesita examinar y ejecutar el script de registro complementario; el programa le permite guardar el script en un archivo de texto que puede enviar posteriormente al DBA de Oracle por correo electrónico o por otros medios para su ejecución posterior (mediante la utilidad SQL\*Plus de Oracle u otra herramienta para ejecutar scripts en una base de datos de Oracle).</span><span class="sxs-lookup"><span data-stu-id="bd9b3-116">This is used if an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script, the program lets you save the script to a text file that you can later send to the Oracle DBA by email or by other means to be execute later (by using the SQL\*Plus Oracle utility or other tool for running scripts on an Oracle database).</span></span>  
  
 <span data-ttu-id="bd9b3-117">**Copy**</span><span class="sxs-lookup"><span data-stu-id="bd9b3-117">**Copy**</span></span>  
 <span data-ttu-id="bd9b3-118">Copia el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-118">Copies the script to the clipboard.</span></span> <span data-ttu-id="bd9b3-119">Cuando esté listo, puede pegar el script en cualquier ubicación que desee por si un administrador de bases de datos (DBA) de Oracle necesita examinar y ejecutar el script de registro complementario.</span><span class="sxs-lookup"><span data-stu-id="bd9b3-119">When ready you can paste the script in any location you need in case an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9b3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd9b3-120">See Also</span></span>  
 <span data-ttu-id="bd9b3-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="bd9b3-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="bd9b3-122">Administrar una instancia CDC</span><span class="sxs-lookup"><span data-stu-id="bd9b3-122">Manage a CDC Instance</span></span>](manage-a-cdc-instance.md)  
  
  
