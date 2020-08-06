---
title: Información general sobre los atributos personalizados de la integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- custom attributes [CLR integration]
- attributes [CLR integration]
- common language runtime [SQL Server], attributes
- database objects [CLR integration], custom attributes
- building database objects [CLR integration], custom attributes
ms.assetid: ecf5c097-0972-48e2-a9c0-b695b7dd2820
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: aa0bf94ee27fd89a6aa690e0ff2f8e3295648946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663095"
---
# <a name="overview-of-clr-integration-custom-attributes"></a><span data-ttu-id="b69be-102">Información general de los atributos personalizados de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="b69be-102">Overview of CLR Integration Custom Attributes</span></span>
  <span data-ttu-id="b69be-103">El Common Language Runtime (CLR) de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] permite el uso de palabras clave descriptivas, llamadas atributos.</span><span class="sxs-lookup"><span data-stu-id="b69be-103">The common language runtime (CLR) of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] allows the use of descriptive keywords, called attributes.</span></span> <span data-ttu-id="b69be-104">Estos atributos proporcionan información adicional para muchos elementos, tales como métodos y clases.</span><span class="sxs-lookup"><span data-stu-id="b69be-104">These attributes provide additional information for many elements, such as methods and classes.</span></span> <span data-ttu-id="b69be-105">Los atributos se guardan en el ensamblado con los metadatos del objeto y se pueden utilizar para describir el código a otras herramientas de desarrollo, o para alterar el comportamiento en tiempo de ejecución dentro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b69be-105">The attributes are saved in the assembly with the metadata of the object, and can be used to describe your code to other development tools or to affect runtime behavior inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b69be-106">Al registrar una rutina CLR con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deriva un conjunto de propiedades sobre la rutina.</span><span class="sxs-lookup"><span data-stu-id="b69be-106">When you register a CLR routine with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives a set of properties about the routine.</span></span> <span data-ttu-id="b69be-107">Estas propiedades rutinarias determinan las capacidades de la rutina, incluido si se puede indizar la rutina.</span><span class="sxs-lookup"><span data-stu-id="b69be-107">These routine properties determine the capabilities of the routine, including whether the routine can be indexed.</span></span> <span data-ttu-id="b69be-108">Por ejemplo, establecer la propiedad `DataAccess` en `DataAccessKind.Read` permite tener acceso a datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dentro de una función CLR.</span><span class="sxs-lookup"><span data-stu-id="b69be-108">For example, setting the `DataAccess` property to `DataAccessKind.Read` lets you access data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user tables inside a CLR function.</span></span> <span data-ttu-id="b69be-109">En el ejemplo siguiente se muestra un caso simple en el que la `DataAccess` propiedad se establece para facilitar el acceso a datos desde una tabla de usuario **Table1**.</span><span class="sxs-lookup"><span data-stu-id="b69be-109">The following example shows a simple case in which the `DataAccess` property is set to facilitate data access from a user table **table1**.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public partial class UserDefinedFunctions  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static string func1()  
    {  
        // Open a connection and create a command  
        SqlConnection conn = new SqlConnection("context connection = true");  
        conn.Open();  
        SqlCommand cmd = conn.CreateCommand();  
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10";  
        // where table1 is a user table  
        // Execute this command   
        SqlDataReader rd = cmd.ExecuteReader();  
        // Set string ret_val to str_val returned from the query  
        string ret_val = rd.GetValue(0).ToString();  
        rd.Close();  
        return ret_val;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public partial Class UserDefinedFunctions  
    <SqlFunction(DataAccess = DataAccessKind.Read)> _   
    Public Shared Function func1() As String  
        ' Open a connection and create a command  
        Dim conn As SqlConnection = New SqlConnection("context connection = true")   
        conn.Open()  
        Dim cmd As SqlCommand =  conn.CreateCommand()   
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10"  
        ' where table1 is a user table  
        ' Execute this command   
        Dim rd As SqlDataReader =  cmd.ExecuteReader()   
        ' Set string ret_val to str_val returned from the query  
        Dim ret_val As String =  rd.GetValue(0).ToString()   
        rd.Close()  
        Return ret_val  
    End Function  
End Class  
```  
  
 <span data-ttu-id="b69be-110">Para las rutinas [!INCLUDE[tsql](../../includes/tsql-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deriva directamente las propiedades de la rutina de la definición de rutina.</span><span class="sxs-lookup"><span data-stu-id="b69be-110">For [!INCLUDE[tsql](../../includes/tsql-md.md)] routines, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives routine properties directly from the routine definition.</span></span> <span data-ttu-id="b69be-111">Para las rutinas CLR, el servidor no analiza el cuerpo de la rutina para derivar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="b69be-111">For CLR routines, the server does not analyze the body of the routine to derive these properties.</span></span> <span data-ttu-id="b69be-112">En su lugar, puede utilizar atributos personalizados para las clases y miembros de clase implementados en un lenguaje [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b69be-112">Instead, you can use custom attributes for classes and class members implemented in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language.</span></span>  
  
 <span data-ttu-id="b69be-113">Los atributos personalizados necesarios para las rutinas CLR, los tipos definidos por el usuario y los agregados se definen en el espacio de nombres `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="b69be-113">The custom attributes needed for CLR routines, user-defined types, and aggregates are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69be-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b69be-114">See Also</span></span>  
 [<span data-ttu-id="b69be-115">Atributos personalizados para las rutinas CLR</span><span class="sxs-lookup"><span data-stu-id="b69be-115">Custom Attributes for CLR Routines</span></span>](../../relational-databases/clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)  
  
  
