---
title: Modificar SQL Server propiedades avanzadas del servicio con VBScript | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- VBScript [WMI]
- modifying SQL Server Service properties
- WMI Provider for Configuration Management, VBScript
ms.assetid: f3c5d981-eaa3-4d34-9b91-37e42636aa81
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cf722b00a31723b77624c33fef81a82ff0cb926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677451"
---
# <a name="modify-sql-server-service-advanced-properties-using-vbscript"></a><span data-ttu-id="7d346-102">Modificar propiedades avanzadas de servicios SQL Server mediante VBScript</span><span class="sxs-lookup"><span data-stu-id="7d346-102">Modify SQL Server Service Advanced Properties using VBScript</span></span>
  <span data-ttu-id="7d346-103">En esta sección se describe cómo crear un programa de VBScript que muestre la versión de las instancias instaladas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecutan en un equipo.</span><span class="sxs-lookup"><span data-stu-id="7d346-103">This section describes how to create a VBScript program that lists the version of installed instances of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are running on a computer.</span></span>  
  
 <span data-ttu-id="7d346-104">En el ejemplo de código se muestran las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecutan en el equipo y su versión.</span><span class="sxs-lookup"><span data-stu-id="7d346-104">The code example lists the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer and its version.</span></span>  
  
### <a name="listing-name-and-version-of-installed-instances-of-sql-server"></a><span data-ttu-id="7d346-105">Mostrar el nombre y la versión de las instancias instaladas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d346-105">Listing name and version of installed instances of SQL Server</span></span>  
  
1.  <span data-ttu-id="7d346-106">Abra un nuevo documento en un editor de texto, como el Bloc de notas de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d346-106">Open a new document in a text editor, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Notepad.</span></span> <span data-ttu-id="7d346-107">Copie el código incluido después de este procedimiento y guarde el archivo con la extensión .vbs.</span><span class="sxs-lookup"><span data-stu-id="7d346-107">Copy the code that follows this procedure and save the file with a .vbs extension.</span></span> <span data-ttu-id="7d346-108">Este ejemplo se denomina test.vbs.</span><span class="sxs-lookup"><span data-stu-id="7d346-108">This example is called test.vbs.</span></span>  
  
2.  <span data-ttu-id="7d346-109">Conéctese a una instancia del proveedor WMI para la Administración de equipos con la función de VBScript `GetObject`.</span><span class="sxs-lookup"><span data-stu-id="7d346-109">Connect to an instance of the WMI Provider for Computer Management with the VBScript `GetObject` function.</span></span> <span data-ttu-id="7d346-110">Este ejemplo se conecta a un equipo remoto denominado mpc, pero omita el nombre de equipo para conectarse al equipo local: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span><span class="sxs-lookup"><span data-stu-id="7d346-110">This example connects to a remote computer named mpc, but omit the computer name to connect to the local computer: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span></span> <span data-ttu-id="7d346-111">Para obtener más información sobre la función `GetObject`, vea la referencia de VBScript.</span><span class="sxs-lookup"><span data-stu-id="7d346-111">For more information about the `GetObject` function, see the VBScript reference.</span></span>  
  
3.  <span data-ttu-id="7d346-112">Utilice el método `InstancesOf` para mostrar una lista de los servicios.</span><span class="sxs-lookup"><span data-stu-id="7d346-112">Use the `InstancesOf` method to enumerate a list of the services.</span></span> <span data-ttu-id="7d346-113">Los servicios también se pueden mostrar mediante una consulta WQL simple y un método `ExecQuery` en lugar del método `InstancesOf`.</span><span class="sxs-lookup"><span data-stu-id="7d346-113">The services can also be enumerated by using a simple WQL query and an `ExecQuery` method instead of the `InstancesOf` method.</span></span>  
  
4.  <span data-ttu-id="7d346-114">Utilice el método `ExecQuery` y una consulta WQL para recuperar el nombre y la versión de las instancias instaladas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d346-114">Use the `ExecQuery` method and a WQL query to retrieve the name and version of the installed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="7d346-115">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="7d346-115">Save the file.</span></span>  
  
6.  <span data-ttu-id="7d346-116">Ejecute el script escribiendo `cscript test.vbs` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7d346-116">Run the script by typing `cscript test.vbs` at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d346-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d346-117">Example</span></span>  
  
```  
set wmi = GetObject("WINMGMTS:\\.\root\Microsoft\SqlServer\ComputerManagement12")  
for each prop in wmi.ExecQuery("select * from SqlServiceAdvancedProperty where SQLServiceType = 1 AND PropertyName = 'VERSION'")  
WScript.Echo prop.ServiceName & " " & prop.PropertyName & ": " & prop.PropertyStrValue  
next  
```  
  
  
