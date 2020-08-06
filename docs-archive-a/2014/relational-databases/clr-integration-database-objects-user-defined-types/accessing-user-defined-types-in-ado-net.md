---
title: Obtener acceso a tipos definidos por el usuario en ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: a94e333ad743ed07dff6b973ebfe227312a1cab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675440"
---
# <a name="accessing-user-defined-types-in-adonet"></a><span data-ttu-id="add78-102">Obtener acceso a tipos definidos por el usuario en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="add78-102">Accessing User-Defined Types in ADO.NET</span></span>
  <span data-ttu-id="add78-103">Los tipos definidos por el usuario (UDT) se escriben utilizando cualquiera de los lenguajes admitidos por el [!INCLUDE[msCoName](../../includes/msconame-md.md)] Common Language Runtime de .NET Framework (CLR) que produce código comprobable.</span><span class="sxs-lookup"><span data-stu-id="add78-103">User-defined types (UDTs) are written using any of the languages supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="add78-104">Esto incluye [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# y [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="add78-104">This includes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span></span> <span data-ttu-id="add78-105">Los UDT permiten almacenar objetos y estructuras de datos personalizadas en una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="add78-105">UDTs allow objects and custom data structures to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="add78-106">Los datos se exponen como miembros públicos de una clase o estructura de .NET Framework y los comportamientos se definen mediante métodos de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="add78-106">The data is exposed as public members of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span> <span data-ttu-id="add78-107">Un UDT puede usarse como la definición de columna de una tabla, como una variable de un lote [!INCLUDE[tsql](../../includes/tsql-md.md)] o como un argumento de una función o procedimiento almacenado [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="add78-107">A UDT can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
 <span data-ttu-id="add78-108">En ADO.NET, el proveedor `System.Data.SqlClient` expone los UDT de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="add78-108">In ADO.NET, the `System.Data.SqlClient` provider exposes UDTs in the following ways:</span></span>  
  
-   <span data-ttu-id="add78-109">A través de `System.Data.SqlClient.SqlDataReader` como un objeto.</span><span class="sxs-lookup"><span data-stu-id="add78-109">Through the `System.Data.SqlClient.SqlDataReader` as an object.</span></span>  
  
-   <span data-ttu-id="add78-110">A través de `SqlDataReader` como bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="add78-110">Through the `SqlDataReader` as raw bytes.</span></span>  
  
-   <span data-ttu-id="add78-111">Como un parámetro de un objeto `System.Data.SqlClient.SqlParameter`.</span><span class="sxs-lookup"><span data-stu-id="add78-111">As a parameter of a `System.Data.SqlClient.SqlParameter` object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="add78-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="add78-112">In This Section</span></span>  
 [<span data-ttu-id="add78-113">Recuperar datos UDT</span><span class="sxs-lookup"><span data-stu-id="add78-113">Retrieving UDT Data</span></span>](accessing-user-defined-types-retrieving-udt-data.md)  
 <span data-ttu-id="add78-114">Describe cómo recuperar los datos UDT y cómo especificar parámetros.</span><span class="sxs-lookup"><span data-stu-id="add78-114">Describes how to retrieve UDT data and how to specify parameters.</span></span>  
  
 [<span data-ttu-id="add78-115">Actualizar columnas de UDT con DataAdapters</span><span class="sxs-lookup"><span data-stu-id="add78-115">Updating UDT Columns with DataAdapters</span></span>](accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 <span data-ttu-id="add78-116">Describe cómo trabajar con UDT en `DataSets` y cómo actualizar datos UDT mediante `DataAdapters`.</span><span class="sxs-lookup"><span data-stu-id="add78-116">Describes how to work with UDTs in `DataSets` and how to update UDT data using `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add78-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="add78-117">See Also</span></span>  
 [<span data-ttu-id="add78-118">Tipos definidos por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="add78-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
