---
title: Ejecutar archivos de scripts Transact-SQL mediante sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
author: rothja
ms.author: jroth
ms.openlocfilehash: cd34b089fc4e971cac9e5713cbe303192a7a48c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669581"
---
# <a name="run-transact-sql-script-files-using-sqlcmd"></a><span data-ttu-id="b2ce7-102">Ejecutar archivos de scripts Transact-SQL mediante sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b2ce7-102">Run Transact-SQL Script Files Using sqlcmd</span></span>
  <span data-ttu-id="b2ce7-103">Puede utilizar `sqlcmd` para ejecutar un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2ce7-103">You can use `sqlcmd` to run a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="b2ce7-104">Un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] es un archivo de texto que puede incluir una combinación de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)], comandos `sqlcmd` y variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-104">A [!INCLUDE[tsql](../../includes/tsql-md.md)] script file is a text file that can contain a combination of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="b2ce7-105">Para crear un archivo sencillo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] mediante el Bloc de notas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b2ce7-105">To create a simple [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using Notepad, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b2ce7-106">Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**y, a continuación, haga clic en **Bloc de notas**.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-106">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad**.</span></span>  
  
2.  <span data-ttu-id="b2ce7-107">Copie y pegue el siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] en el Bloc de notas:</span><span class="sxs-lookup"><span data-stu-id="b2ce7-107">Copy and paste the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code into Notepad:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  <span data-ttu-id="b2ce7-108">Guarde el archivo como **myScript.sql** en la unidad C.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-108">Save the file as **myScript.sql** in the C drive.</span></span>  
  
### <a name="to-run-the-script-file"></a><span data-ttu-id="b2ce7-109">Para ejecutar el archivo de script</span><span class="sxs-lookup"><span data-stu-id="b2ce7-109">To run the script file</span></span>  
  
1.  <span data-ttu-id="b2ce7-110">Abra una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-110">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="b2ce7-111">En la ventana de símbolo del sistema, escriba: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span><span class="sxs-lookup"><span data-stu-id="b2ce7-111">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span></span>  
  
3.  <span data-ttu-id="b2ce7-112">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-112">Press ENTER.</span></span>  
  
 <span data-ttu-id="b2ce7-113">En la ventana del símbolo del sistema se escribe una lista con las direcciones y los nombres de los empleados que figuran en [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2ce7-113">A list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] employee names and addresses is written to the command prompt window.</span></span>  
  
### <a name="to-save-this-output-to-a-text-file"></a><span data-ttu-id="b2ce7-114">Para guardar los resultados en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="b2ce7-114">To save this output to a text file</span></span>  
  
1.  <span data-ttu-id="b2ce7-115">Abra una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-115">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="b2ce7-116">En la ventana de símbolo del sistema, escriba: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span><span class="sxs-lookup"><span data-stu-id="b2ce7-116">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span></span>  
  
3.  <span data-ttu-id="b2ce7-117">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-117">Press ENTER.</span></span>  
  
 <span data-ttu-id="b2ce7-118">La ventana del símbolo del sistema no devuelve resultados.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-118">No output is returned in the Command Prompt window.</span></span> <span data-ttu-id="b2ce7-119">En su lugar, los resultados se envían al archivo EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-119">Instead, the output is sent to the EmpAdds.txt file.</span></span> <span data-ttu-id="b2ce7-120">Para comprobar los resultados, abra el archivo EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="b2ce7-120">You can verify this output by opening the EmpAdds.txt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ce7-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2ce7-121">See Also</span></span>  
 <span data-ttu-id="b2ce7-122">[Iniciar la utilidad sqlcmd](sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b2ce7-122">[Start the sqlcmd Utility](sqlcmd-start-the-utility.md) </span></span>  
 [<span data-ttu-id="b2ce7-123">Utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b2ce7-123">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
