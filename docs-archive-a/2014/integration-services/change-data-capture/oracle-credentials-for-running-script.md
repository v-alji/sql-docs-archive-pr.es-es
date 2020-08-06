---
title: Credenciales de Oracle para ejecutar script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 683b313e5b1065c3709c4637ddf968641612cc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744249"
---
# <a name="oracle-credentials-for-running-script"></a><span data-ttu-id="5681d-102">Credenciales de Oracle para ejecutar script</span><span class="sxs-lookup"><span data-stu-id="5681d-102">Oracle Credentials for Running Script</span></span>
  <span data-ttu-id="5681d-103">Para ejecutar el script de registro complementario de Oracle desde la consola del Diseñador CDC de Oracle, el programa le solicitará las credenciales del usuario de Oracle que está ejecutando el script.</span><span class="sxs-lookup"><span data-stu-id="5681d-103">To run the Oracle supplemental logging script from the Oracle CDC Designer console, the program prompts you for the credentials of the Oracle user who is running the script.</span></span> <span data-ttu-id="5681d-104">Para ejecutar este script, el usuario de Oracle debe tener el permiso ALTER TABLE para todas las tablas que se van a capturar y el permiso SELECT en la vista DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="5681d-104">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="5681d-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="5681d-105">Task List</span></span>  
 <span data-ttu-id="5681d-106">Escriba lo siguiente en este cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="5681d-106">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="5681d-107">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="5681d-107">**Authentication**</span></span>  
  
 <span data-ttu-id="5681d-108">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5681d-108">Select one of the following:</span></span>  
  
-   <span data-ttu-id="5681d-109">**Autenticación de Windows**: seleccione esta opción para usar las credenciales del dominio de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="5681d-109">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="5681d-110">Solo puede usar esta opción si la base de datos de Oracle está configurada para usar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5681d-110">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="5681d-111">**Autenticación de Oracle**: si selecciona esta opción, debe escribir el **Nombre de usuario** y la **Contraseña** para el usuario en la base de datos de Oracle de origen a la que se está conectando.</span><span class="sxs-lookup"><span data-stu-id="5681d-111">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Source Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5681d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5681d-112">See Also</span></span>  
 <span data-ttu-id="5681d-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="5681d-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="5681d-114">Revisar y generar Scripts de registro complementario</span><span class="sxs-lookup"><span data-stu-id="5681d-114">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
