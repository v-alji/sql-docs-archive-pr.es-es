---
title: Construir una instrucción SQL (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
ms.assetid: 0acc71e2-8004-4dd8-8592-05c022bdd692
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c454f936c49335555ca09b190e4d604c9fbad64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662884"
---
# <a name="constructing-an-sql-statement-odbc"></a><span data-ttu-id="366de-102">Crear una instrucción SQL (ODBC)</span><span class="sxs-lookup"><span data-stu-id="366de-102">Constructing an SQL Statement (ODBC)</span></span>
  <span data-ttu-id="366de-103">Las aplicaciones ODBC realizan casi todos sus accesos a bases de datos ejecutando instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="366de-103">ODBC applications perform almost all of their database access by executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="366de-104">El formato de estas instrucciones depende de los requisitos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="366de-104">The form of these statements depends on the application requirements.</span></span> <span data-ttu-id="366de-105">Pueden crearse instrucciones SQL de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="366de-105">SQL statements can be constructed in the following ways:</span></span>  
  
-   <span data-ttu-id="366de-106">Codificadas de forma rígida</span><span class="sxs-lookup"><span data-stu-id="366de-106">Hard-coded</span></span>  
  
     <span data-ttu-id="366de-107">Instrucciones estáticas ejecutadas por una aplicación como una tarea fija.</span><span class="sxs-lookup"><span data-stu-id="366de-107">Static statements performed by an application as a fixed task.</span></span>  
  
-   <span data-ttu-id="366de-108">Creadas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="366de-108">Constructed at run time</span></span>  
  
     <span data-ttu-id="366de-109">Instrucciones SQL creadas en tiempo de ejecución que permiten al usuario personalizar la instrucción utilizando cláusulas comunes, como SELECT, WHERE y ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="366de-109">SQL statements constructed at run time that enable the user to tailor the statement by using common clauses, such as SELECT, WHERE, and ORDER BY.</span></span> <span data-ttu-id="366de-110">Entre este tipo de instrucciones se incluyen las consultas ad hoc escritas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="366de-110">This includes ad hoc queries entered by users.</span></span>  
  
 <span data-ttu-id="366de-111">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de cliente analiza las instrucciones SQL solo para la sintaxis de ODBC e ISO no admitida directamente por [!INCLUDE[ssDE](../../includes/ssde-md.md)] , que el controlador transforma en [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="366de-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client ODBC driver parses SQL statements only for ODBC and ISO syntax not directly supported by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], which the driver transforms into [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="366de-112">El resto de la sintaxis SQL se pasa a [!INCLUDE[ssDE](../../includes/ssde-md.md)] sin modificar, donde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determinará si se trata de código [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] válido.</span><span class="sxs-lookup"><span data-stu-id="366de-112">All other SQL syntax is passed to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] unchanged, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will determine if it is valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="366de-113">Este enfoque ofrece dos ventajas:</span><span class="sxs-lookup"><span data-stu-id="366de-113">This approach yields two benefits:</span></span>  
  
-   <span data-ttu-id="366de-114">Reducción de la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="366de-114">Reduced overhead</span></span>  
  
     <span data-ttu-id="366de-115">El procesamiento de la sobrecarga del controlador se minimiza ya que solo tiene que examinar un conjunto pequeño de las cláusulas ODBC e ISO.</span><span class="sxs-lookup"><span data-stu-id="366de-115">Processing overhead for the driver is minimized because it only has to scan for a small set of ODBC and ISO clauses.</span></span>  
  
-   <span data-ttu-id="366de-116">Flexibilidad</span><span class="sxs-lookup"><span data-stu-id="366de-116">Flexibility</span></span>  
  
     <span data-ttu-id="366de-117">Los programadores pueden personalizar la portabilidad de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="366de-117">Programmers can tailor the portability of their applications.</span></span> <span data-ttu-id="366de-118">Para mejorar la portabilidad en distintas bases de datos, utilice principalmente la sintaxis ODBC e ISO.</span><span class="sxs-lookup"><span data-stu-id="366de-118">To enhance portability against multiple databases, use primarily ODBC and ISO syntax.</span></span> <span data-ttu-id="366de-119">Para utilizar mejoras específicas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use la sintaxis [!INCLUDE[tsql](../../includes/tsql-md.md)] adecuada.</span><span class="sxs-lookup"><span data-stu-id="366de-119">To use enhancements specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the appropriate [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="366de-120">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite la [!INCLUDE[tsql](../../includes/tsql-md.md)] sintaxis completa, por lo que las aplicaciones basadas en ODBC pueden aprovechar todas las características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="366de-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the complete [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax so ODBC-based applications can take advantage of all the features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="366de-121">La lista de columnas de una instrucción SELECT solo debe incluir las columnas necesarias para realizar la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="366de-121">The column list in a SELECT statement should contain only the columns required to perform the current task.</span></span> <span data-ttu-id="366de-122">Esto no solo hace que se reduzca la cantidad de datos enviados a través de la red, sino que también reduce el efecto de los cambios de la base de datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="366de-122">Not only does this reduce the amount of data sent across the network, but also it reduces the effect of database changes on the application.</span></span> <span data-ttu-id="366de-123">Si una aplicación no hace referencia a una columna de una tabla, cualquier cambio que se realice en dicha columna no afectará a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="366de-123">If an application does not reference a column from a table, then the application is not affected by any changes made to that column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="366de-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="366de-124">See Also</span></span>  
 [<span data-ttu-id="366de-125">Ejecutar consultas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="366de-125">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
