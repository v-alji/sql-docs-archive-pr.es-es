---
title: Descargar una DLL de procedimiento almacenado extendido | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], unloading
- unloading extended stored procedures
ms.assetid: 4c75ab14-af54-4965-b376-8d75d385c941
author: rothja
ms.author: jroth
ms.openlocfilehash: 7bd4855390e95d949ab769d6567d6f106959dcde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662032"
---
# <a name="unloading-an-extended-stored-procedure-dll"></a><span data-ttu-id="703e8-102">Descargar una DLL de procedimiento almacenado extendido</span><span class="sxs-lookup"><span data-stu-id="703e8-102">Unloading an Extended Stored Procedure DLL</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="703e8-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="703e8-103">Use CLR Integration instead.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="703e8-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]carga una DLL de procedimiento almacenado extendido en cuanto se realiza una llamada a una de las funciones del archivo dll.</span><span class="sxs-lookup"><span data-stu-id="703e8-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads an extended stored procedure DLL as soon as a call is made to one of the functions of the DLL.</span></span> <span data-ttu-id="703e8-105">La DLL sigue cargada hasta que se cierra el servidor o hasta que el administrador del sistema utiliza la instrucción DBCC para descargarla.</span><span class="sxs-lookup"><span data-stu-id="703e8-105">The DLL remains loaded until the server is shut down or until the system administrator uses the DBCC statement to unload it.</span></span> <span data-ttu-id="703e8-106">Por ejemplo, este comando descarga el **xp_hello.dll**, lo que permite al administrador del sistema copiar una versión más reciente de este archivo en el directorio sin apagar el servidor:</span><span class="sxs-lookup"><span data-stu-id="703e8-106">For example, this command unloads the **xp_hello.dll**, allowing the system administrator to copy a newer version of this file to the directory without shutting down the server:</span></span>  
  
```  
DBCC xp_hello(FREE)  
```  
  
## <a name="see-also"></a><span data-ttu-id="703e8-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="703e8-107">See Also</span></span>  
 [<span data-ttu-id="703e8-108">DBCC DllName &#40;FREE&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="703e8-108">DBCC dllname &#40;FREE&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dllname-free-transact-sql)  
  
  
