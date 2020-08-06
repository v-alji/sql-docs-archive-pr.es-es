---
title: Cómo funcionan los procedimientos almacenados extendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], about extended stored procedures
ms.assetid: 6e946d8c-3268-4b59-8a1c-1637909cd701
author: rothja
ms.author: jroth
ms.openlocfilehash: 75082fed6b70c214b4f55b85034ffa371824d24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675388"
---
# <a name="how-extended-stored-procedures-work"></a><span data-ttu-id="fa3f9-102">Cómo funcionan los procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="fa3f9-102">How Extended Stored Procedures Work</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fa3f9-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="fa3f9-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="fa3f9-104">El procedimiento almacenado extendido funciona del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="fa3f9-104">The process by which an extended stored procedure works is:</span></span>  
  
1.  <span data-ttu-id="fa3f9-105">Cuando un cliente ejecuta un procedimiento almacenado extendido, la solicitud se transmite en formato de flujo de datos tabular (TDS) o de Protocolo simple de acceso a objetos (SOAP) desde la aplicación cliente a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa3f9-105">When a client executes an extended stored procedure, the request is transmitted in tabular data stream (TDS) or Simple Object Access Protocol (SOAP) format from the client application to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fa3f9-106">busca la DLL asociada al procedimiento almacenado extendido y la carga si no lo está ya.</span><span class="sxs-lookup"><span data-stu-id="fa3f9-106">searches for the DLL associated with the extended stored procedure, and loads the DLL if it is not already loaded.</span></span>  
  
3.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fa3f9-107">llama al procedimiento almacenado extendido solicitado (está implementado como una función dentro de la DLL).</span><span class="sxs-lookup"><span data-stu-id="fa3f9-107">calls the requested extended stored procedure (implemented as a function inside the DLL).</span></span>  
  
4.  <span data-ttu-id="fa3f9-108">El procedimiento almacenado extendido pasa conjuntos de resultados y devuelve parámetros de retorno al servidor mediante la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="fa3f9-108">The extended stored procedure passes result sets and return parameters back to the server by through the Extended Stored Procedure API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3f9-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa3f9-109">See Also</span></span>  
 [<span data-ttu-id="fa3f9-110">Programación de procedimientos almacenados extendidos de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="fa3f9-110">Database Engine Extended Stored Procedure Programming</span></span>](../database-engine-extended-stored-procedure-programming.md)  
  
  
