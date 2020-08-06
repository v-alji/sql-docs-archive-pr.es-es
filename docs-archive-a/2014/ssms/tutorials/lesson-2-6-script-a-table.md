---
title: Incluir una tabla en un script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ea88d736-849e-4368-b55d-06aeee097bf3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 247c839d83768756c57297d47f952401a1c8fd46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671294"
---
# <a name="script-a-table"></a><span data-ttu-id="2b316-102">Incluir una tabla en un script</span><span class="sxs-lookup"><span data-stu-id="2b316-102">Script a Table</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="2b316-103">puede crear scripts para seleccionar, insertar, actualizar y eliminar tablas, y para crear, modificar, quitar o ejecutar procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="2b316-103">can create scripts to select, insert, update, and delete tables, and to create, alter, drop, or execute stored procedures.</span></span>  
  
 <span data-ttu-id="2b316-104">En ocasiones, necesitará un script que ofrezca varias opciones como, por ejemplo, quitar un procedimiento y, a continuación, crear otro, o bien crear una tabla y modificarla posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2b316-104">Sometimes you want a script with multiple options, such as drop a procedure and then create a procedure, or create a table then alter a table.</span></span> <span data-ttu-id="2b316-105">Para crear scripts combinados, guarde el primer script en una ventana del Editor de consultas y el segundo en el Portapapeles para poder pegarlo en la ventana a continuación del primero.</span><span class="sxs-lookup"><span data-stu-id="2b316-105">To create combined scripts, save the first script to a Query Editor window and the second to the clipboard so you can paste it into the window after the first script.</span></span>  
  
## <a name="creating-an-update-script"></a><span data-ttu-id="2b316-106">Crear un script de actualización</span><span class="sxs-lookup"><span data-stu-id="2b316-106">Creating an Update Script</span></span>  
  
#### <a name="to-create-the-insert-script-for-a-table"></a><span data-ttu-id="2b316-107">Para crear un script de inserción para una tabla</span><span class="sxs-lookup"><span data-stu-id="2b316-107">To create the insert script for a table</span></span>  
  
1.  <span data-ttu-id="2b316-108">En el Explorador de objetos, expanda el servidor, **Bases de datos**, [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]y **Tablas**; haga clic con el botón derecho en **HumanResources.Employee**y, después, señale **Incluir tabla como**.</span><span class="sxs-lookup"><span data-stu-id="2b316-108">In Object Explorer, expand your server, expand **Databases**, expand [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], expand **Tables**, right-click **HumanResources.Employee**, and then point to **Script Table As**.</span></span>  
  
2.  <span data-ttu-id="2b316-109">El menú contextual tiene siete opciones de scripting disponibles: **CREATE To**, **DROP To**, **DROP y CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**y **DELETE To**.</span><span class="sxs-lookup"><span data-stu-id="2b316-109">The shortcut menu has seven available scripting options: **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**, and **DELETE To**.</span></span> <span data-ttu-id="2b316-110">Seleccione **UPDATE To**y haga clic en **Nueva ventana del Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="2b316-110">Point to **UPDATE To**, and then click **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="2b316-111">Se abre una ventana nueva del Editor de consultas que establece una conexión y presenta la instrucción completa actualizada.</span><span class="sxs-lookup"><span data-stu-id="2b316-111">A new Query Editor window opens, makes a connection, and presents the entire update statement.</span></span>  
  
     <span data-ttu-id="2b316-112">Este ejercicio muestra cómo la característica de scripting puede hacer mucho más que crear un script para una tabla o un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="2b316-112">This exercise demonstrates how the scripting feature can do more than just script the creation of a table or stored procedure.</span></span> <span data-ttu-id="2b316-113">Esta nueva función puede ayudarle a agregar scripts de manipulación de datos a su proyecto y a crear fácilmente script para la ejecución de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="2b316-113">This new feature can help you quickly add data manipulation scripts to your project and easily script execution of stored procedures.</span></span> <span data-ttu-id="2b316-114">Esto puede ahorrarle mucho tiempo en el caso de tablas y procedimientos con muchos campos.</span><span class="sxs-lookup"><span data-stu-id="2b316-114">This can be a big timesaver for tables and procedures with many fields.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2b316-115">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="2b316-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2b316-116">Resumen: Escribir Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b316-116">Summary: Writing Transact-SQL</span></span>](../../tutorials/summary-writing-transact-sql.md)  
  
  
