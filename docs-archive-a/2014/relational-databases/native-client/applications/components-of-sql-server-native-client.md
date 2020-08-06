---
title: Componentes de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], components
- components [SQL Server Native Client]
- SQLNCLI, about SQL Server Native Client
ms.assetid: 65f932d5-daa1-4eff-b6df-ee633fcf2a7c
author: rothja
ms.author: jroth
ms.openlocfilehash: 32438b9fb5473d9251acd0aceddb46db373f3548
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674073"
---
# <a name="components-of-sql-server-native-client"></a><span data-ttu-id="04cfa-102">Componentes de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="04cfa-102">Components of SQL Server Native Client</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="04cfa-103">Native Client contiene los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="04cfa-103">Native Client contains the following components:</span></span>  
  
|<span data-ttu-id="04cfa-104">Componente</span><span class="sxs-lookup"><span data-stu-id="04cfa-104">Component</span></span>|<span data-ttu-id="04cfa-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="04cfa-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04cfa-106">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="04cfa-106">sqlncli11.dll</span></span>|<span data-ttu-id="04cfa-107">El archivo de biblioteca de vínculos dinámicos (DLL) que contiene toda la funcionalidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="04cfa-107">The dynamic-link library (DLL) file that contains all of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client functionality.</span></span> <span data-ttu-id="04cfa-108">Esto incluye el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client y el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="04cfa-108">This includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>|  
|<span data-ttu-id="04cfa-109">sqlnclir11.rll</span><span class="sxs-lookup"><span data-stu-id="04cfa-109">sqlnclir11.rll</span></span>|<span data-ttu-id="04cfa-110">El archivo de recursos adjunto para la biblioteca de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="04cfa-110">The accompanying resource file for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library.</span></span>|  
|<span data-ttu-id="04cfa-111">s10ch_sqlncli.chm</span><span class="sxs-lookup"><span data-stu-id="04cfa-111">s10ch_sqlncli.chm</span></span>|<span data-ttu-id="04cfa-112">El archivo de ayuda del Asistente para orígenes de datos que documenta cómo crear un origen de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client o el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="04cfa-112">The Data Source Wizard help file that documents how to create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data source using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>|  
|<span data-ttu-id="04cfa-113">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="04cfa-113">sqlncli.h</span></span>|<span data-ttu-id="04cfa-114">El archivo de encabezado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client que contiene todas las definiciones nuevas necesarias para utilizar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="04cfa-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header file that contains all of the new definitions needed in order to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="04cfa-115">Este archivo de encabezado reemplaza a los archivos de encabezado odbcss.h y sqloledb.h.</span><span class="sxs-lookup"><span data-stu-id="04cfa-115">This header file replaces both the odbcss.h and the sqloledb.h header files.</span></span> <span data-ttu-id="04cfa-116">**Nota:**  No se puede hacer referencia a SQLNCLI. h y odbcss. h en el mismo programa, pero se puede hacer referencia a SQLNCLI. h y SQLOLEDB. h en el mismo programa, siempre que se defina primero SQLOLEDB. h.</span><span class="sxs-lookup"><span data-stu-id="04cfa-116">**Note:**  You cannot reference sqlncli.h and odbcss.h in the same program, but you can reference sqlncli.h and sqloledb.h in same program as long as sqloledb.h is defined first.</span></span>|  
|<span data-ttu-id="04cfa-117">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="04cfa-117">sqlncli11.lib</span></span>|<span data-ttu-id="04cfa-118">El archivo de biblioteca necesario para llamar directamente a las funciones de la utilidad **BCP** que forman parte del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="04cfa-118">The library file needed to directly call the **bcp** utility functions that are part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="04cfa-119">**Nota:**  Si hace referencia al archivo sqlncli11. lib en el código de programación, debe asegurarse de que el archivo de sqlncli11.dll está en la ruta de acceso del sistema y en la ruta de acceso del sistema de los usuarios que usan la aplicación.</span><span class="sxs-lookup"><span data-stu-id="04cfa-119">**Note:**  If you do reference the sqlncli11.lib file in your programming code, you need to make sure that the sqlncli11.dll file is in your system path, and in the system path of the users that make use of your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04cfa-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04cfa-120">See Also</span></span>  
 [<span data-ttu-id="04cfa-121">Generar aplicaciones con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="04cfa-121">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
