---
title: Usar parámetros de instrucción | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- ODBC, parameters
- statements [ODBC], parameters
- parameter markers [ODBC]
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
ms.assetid: 2427d886-ec6c-49d7-b0b6-0d998b64cdb9
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b7e207416e60af94efd59555980a0edff68a38b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662863"
---
# <a name="using-statement-parameters"></a><span data-ttu-id="02d64-102">Usar parámetros de instrucciones</span><span class="sxs-lookup"><span data-stu-id="02d64-102">Using Statement Parameters</span></span>
  <span data-ttu-id="02d64-103">Un parámetro es una variable en una instrucción SQL que puede habilitar una aplicación ODBC:</span><span class="sxs-lookup"><span data-stu-id="02d64-103">A parameter is a variable in an SQL statement that can enable an ODBC application to:</span></span>  
  
-   <span data-ttu-id="02d64-104">Proporcionando de forma eficaz valores para las columnas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="02d64-104">Efficiently provide values for columns in a table.</span></span>  
  
-   <span data-ttu-id="02d64-105">Mejorando la interacción del usuario para construir criterios de consulta.</span><span class="sxs-lookup"><span data-stu-id="02d64-105">Enhance user interaction in constructing query criteria.</span></span>  
  
-   <span data-ttu-id="02d64-106">Administrar datos de tipo **Text**, **ntext**e **Image** y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos de C específicos.</span><span class="sxs-lookup"><span data-stu-id="02d64-106">Manage **text**, **ntext**, and **image** data and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types.</span></span>  
  
 <span data-ttu-id="02d64-107">Por ejemplo, una tabla **Parts** tiene columnas **denominadas**el nombre del campo, la **Descripción**y el **precio**.</span><span class="sxs-lookup"><span data-stu-id="02d64-107">For example, a **Parts** table has columns named **PartID**, **Description**, and **Price**.</span></span> <span data-ttu-id="02d64-108">Para agregar una parte sin parámetros se requiere la construcción de una instrucción SQL como:</span><span class="sxs-lookup"><span data-stu-id="02d64-108">To add a part without parameters requires constructing an SQL statement such as:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (2100, 'Drive shaft', 50.00)  
```  
  
 <span data-ttu-id="02d64-109">Aunque esta instrucción es aceptable para insertar una fila con un conjunto conocido de valores, resulta complicado cuando se requiere que una aplicación inserte varias filas.</span><span class="sxs-lookup"><span data-stu-id="02d64-109">Although this statement is acceptable for inserting one row with a known set of values, it is awkward when an application is required to insert several rows.</span></span> <span data-ttu-id="02d64-110">ODBC soluciona esto permitiendo que una aplicación reemplace cualquier valor de datos en una instrucción SQL mediante un creador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="02d64-110">ODBC addresses this by letting an application to replace any data value in an SQL statement by a parameter maker.</span></span> <span data-ttu-id="02d64-111">Esto se indica mediante un signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="02d64-111">This is denoted by a question mark (?).</span></span> <span data-ttu-id="02d64-112">En el ejemplo siguiente, tres valores de datos se reemplazan con marcadores de parámetros:</span><span class="sxs-lookup"><span data-stu-id="02d64-112">In the following example, three data values are replaced with parameter markers:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="02d64-113">Los marcadores de parámetros se enlazan a variables de aplicación.</span><span class="sxs-lookup"><span data-stu-id="02d64-113">The parameter markers are then bound to application variables.</span></span> <span data-ttu-id="02d64-114">Para insertar una nueva fila, la aplicación únicamente tiene que establecer los valores de las variables y ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="02d64-114">To insert a new row, the application has only to set the values of the variables and execute the statement.</span></span> <span data-ttu-id="02d64-115">Después, el controlador recupera los valores actuales de las variables y los envía al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="02d64-115">The driver then retrieves the current values of the variables and sends them to the data source.</span></span> <span data-ttu-id="02d64-116">Si se ejecuta la instrucción varias veces, la aplicación puede hacer que el proceso mejore al preparar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="02d64-116">If the statement is executed multiple times, the application can make the process even more efficient by preparing the statement.</span></span>  
  
 <span data-ttu-id="02d64-117">Cada número ordinal asignado a los parámetros de izquierda a derecha hace referencia a su marcador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="02d64-117">Each parameter marker is referenced by its ordinal number assigned to the parameters from left to right.</span></span> <span data-ttu-id="02d64-118">El marcador de parámetros del extremo izquierdo de una instrucción SQL tiene un valor ordinal de 1; el siguiente es el ordinal 2, etc.</span><span class="sxs-lookup"><span data-stu-id="02d64-118">The leftmost parameter marker in an SQL statement has an ordinal value of 1; the next one is ordinal 2, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02d64-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="02d64-119">In This Section</span></span>  
  
-   [<span data-ttu-id="02d64-120">Enlazar parámetros</span><span class="sxs-lookup"><span data-stu-id="02d64-120">Binding Parameters</span></span>](using-statement-parameters-binding-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="02d64-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02d64-121">See Also</span></span>  
 [<span data-ttu-id="02d64-122">Ejecutar consultas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="02d64-122">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
