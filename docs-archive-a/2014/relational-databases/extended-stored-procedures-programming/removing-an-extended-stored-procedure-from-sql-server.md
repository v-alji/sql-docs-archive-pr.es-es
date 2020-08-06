---
title: Quitar un procedimiento almacenado extendido de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.openlocfilehash: 284da815de073248669da032c06ddeeb68c697a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752154"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a><span data-ttu-id="def9b-102">Quitar un procedimiento almacenado extendido de SQL Server</span><span class="sxs-lookup"><span data-stu-id="def9b-102">Removing an Extended Stored Procedure from SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="def9b-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="def9b-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="def9b-104">Para quitar cada función de procedimiento almacenado extendido en un archivo DLL de procedimiento almacenado extendido definido por el usuario, un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Administrador del sistema debe ejecutar el **sp_dropextendedproc** procedimiento almacenado del sistema, especificando el nombre de la función y el nombre del archivo dll en el que reside dicha función.</span><span class="sxs-lookup"><span data-stu-id="def9b-104">To drop each extended stored procedure function in a user-defined extended stored procedure DLL, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must run the **sp_dropextendedproc** system stored procedure, specifying the name of the function and the name of the DLL in which that function resides.</span></span> <span data-ttu-id="def9b-105">Por ejemplo, este comando quita la función **xp_hello**, ubicada en un archivo DLL denominado xp_hello.dll, de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="def9b-105">For example, this command removes the function **xp_hello**, located in a DLL named xp_hello.dll, from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="def9b-106">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , **sp_dropextendedproc** no quita los procedimientos almacenados extendidos del sistema.</span><span class="sxs-lookup"><span data-stu-id="def9b-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], **sp_dropextendedproc** does not drop system extended stored procedures.</span></span> <span data-ttu-id="def9b-107">En su lugar, el administrador del sistema debe denegar el permiso EXECUTe para el procedimiento almacenado extendido al rol **Public** .</span><span class="sxs-lookup"><span data-stu-id="def9b-107">Instead, the system administrator should deny EXECUTE permission on the extended stored procedure to the **public** role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def9b-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="def9b-108">See Also</span></span>  
 [<span data-ttu-id="def9b-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="def9b-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
