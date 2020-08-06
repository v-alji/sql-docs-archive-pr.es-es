---
title: Características de ejecución de procedimientos almacenados extendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], executing
- executing extended stored procedures [SQL Server]
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
author: rothja
ms.author: jroth
ms.openlocfilehash: edbd73797699d65f694e91bc3035e0dc9366c9d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663489"
---
# <a name="execution-characteristics-of-extended-stored-procedures"></a><span data-ttu-id="4bf55-102">Características de ejecución de los procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="4bf55-102">Execution Characteristics of Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4bf55-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="4bf55-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="4bf55-104">La ejecución de un procedimiento almacenado extendido tiene estas características:</span><span class="sxs-lookup"><span data-stu-id="4bf55-104">The execution of an extended stored procedure has these characteristics:</span></span>  
  
-   <span data-ttu-id="4bf55-105">La función de procedimiento almacenado extendido se ejecuta en el contexto de seguridad de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bf55-105">The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4bf55-106">La función de procedimiento almacenado extendido se ejecuta en el espacio de procesos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bf55-106">The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4bf55-107">El subproceso asociado a la ejecución del procedimiento almacenado extendido es el mismo que se utiliza para la conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="4bf55-107">The thread associated with the execution of the extended stored procedure is the same one used for the client connection.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4bf55-108">Antes de agregar procedimientos almacenados extendidos al servidor y otorgar permisos de ejecución a otros usuarios, el administrador del sistema debe revisar por completo cada procedimiento almacenado extendido para asegurarse de que no contiene código perjudicial o dañino.</span><span class="sxs-lookup"><span data-stu-id="4bf55-108">Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.</span></span>  
  
-  
  
 <span data-ttu-id="4bf55-109">Una vez cargado el archivo DLL de procedimiento almacenado extendido, el archivo DLL permanece cargado en el espacio de direcciones del servidor hasta que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se detiene o el administrador descarga explícitamente el archivo DLL mediante DBCC *DLL_name* (Free).</span><span class="sxs-lookup"><span data-stu-id="4bf55-109">After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).</span></span>  
  
 <span data-ttu-id="4bf55-110">El procedimiento almacenado extendido se puede ejecutar desde [!INCLUDE[tsql](../../includes/tsql-md.md)] como un procedimiento almacenado utilizando la instrucción EXECUTE:</span><span class="sxs-lookup"><span data-stu-id="4bf55-110">The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:</span></span>  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bf55-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bf55-111">Parameters</span></span>  
 <span data-ttu-id="4bf55-112">\@ *retval*</span><span class="sxs-lookup"><span data-stu-id="4bf55-112">\@ *retval*</span></span>  
 <span data-ttu-id="4bf55-113">Es un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4bf55-113">Is a return value.</span></span>  
  
 <span data-ttu-id="4bf55-114">\@*parám1*</span><span class="sxs-lookup"><span data-stu-id="4bf55-114">\@ *param1*</span></span>  
 <span data-ttu-id="4bf55-115">Es un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="4bf55-115">Is an input parameter.</span></span>  
  
 <span data-ttu-id="4bf55-116">\@*parám2*</span><span class="sxs-lookup"><span data-stu-id="4bf55-116">\@ *param2*</span></span>  
 <span data-ttu-id="4bf55-117">Es un parámetro de entrada/salida.</span><span class="sxs-lookup"><span data-stu-id="4bf55-117">Is an input/output parameter.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4bf55-118">Los procedimientos almacenados extendidos proporcionan mejoras de rendimiento y amplían la funcionalidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bf55-118">Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="4bf55-119">No obstante, como la DLL de procedimiento almacenado extendido y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comparten el mismo espacio de direcciones, un procedimiento con problemas puede afectar de forma negativa al funcionamiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bf55-119">However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning.</span></span> <span data-ttu-id="4bf55-120">Aunque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administra las excepciones generadas por la DLL de procedimiento almacenado extendido, es posible que las áreas de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resulten dañadas.</span><span class="sxs-lookup"><span data-stu-id="4bf55-120">Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas.</span></span> <span data-ttu-id="4bf55-121">Como medida de seguridad preventiva, solo los administradores del sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden agregar los procedimientos almacenados extendidos a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bf55-121">As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4bf55-122">Antes de instalar estos procedimientos, se deberían probar con detenimiento.</span><span class="sxs-lookup"><span data-stu-id="4bf55-122">These procedures should be thoroughly tested before they are installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf55-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bf55-123">See Also</span></span>  
 <span data-ttu-id="4bf55-124">[Programar procedimientos almacenados extendidos](database-engine-extended-stored-procedures-programming.md) </span><span class="sxs-lookup"><span data-stu-id="4bf55-124">[Programming Extended Stored Procedures](database-engine-extended-stored-procedures-programming.md) </span></span>  
 [<span data-ttu-id="4bf55-125">Consultar procedimientos almacenados extendidos instalados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="4bf55-125">Querying Extended Stored Procedures Installed in SQL Server</span></span>](querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
