---
title: Enviar conjuntos de resultados al servidor (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], sending result sets
- result sets [SQL Server], extended stored procedures
ms.assetid: 9d54673d-ea9d-4ac6-825a-f216ad8b0e34
author: rothja
ms.author: jroth
ms.openlocfilehash: 82984440f96416189eb18f900764ee7bdaf05a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662038"
---
# <a name="sending-result-sets-to-the-server-extended-stored-procedure-api"></a><span data-ttu-id="1f17e-102">Enviar conjuntos de resultados al servidor (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="1f17e-102">Sending Result Sets to the Server (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1f17e-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="1f17e-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="1f17e-104">Al enviar un conjunto de resultados a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el procedimiento almacenado extendido debe llamar a la API adecuada de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1f17e-104">When sending a result set to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the extended stored procedure should call the appropriate API as follows:</span></span>  
  
-   <span data-ttu-id="1f17e-105">Se puede llamar a la función **srv_sendmsg** en cualquier orden antes o después de que todas las filas (si las hubiera) se hayan enviado con **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="1f17e-105">The **srv_sendmsg** function may be called in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="1f17e-106">Todos los mensajes se deben enviar al cliente antes de que el estado de finalización se envíe con **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="1f17e-106">All messages must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="1f17e-107">Se llama a la función **srv_sendrow** una vez por cada fila enviada al cliente.</span><span class="sxs-lookup"><span data-stu-id="1f17e-107">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="1f17e-108">Todas las filas se deben enviar al cliente antes de enviar cualquier mensaje, valor de estado o estado de finalización con **srv_sendmsg**, el argumento de **srv_status** de **srv_pfield**o **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="1f17e-108">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, the **srv_status** argument of **srv_pfield**, or **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="1f17e-109">El envío de una fila en la que no se han definido todas sus columnas con **srv_describe** hace que la aplicación genere un mensaje de error informativo y devuelva FAIL al cliente.</span><span class="sxs-lookup"><span data-stu-id="1f17e-109">Sending a row that has not had all its columns defined with **srv_describe** causes the application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="1f17e-110">En este caso, la fila no se envía.</span><span class="sxs-lookup"><span data-stu-id="1f17e-110">In this case, the row is not sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f17e-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f17e-111">See Also</span></span>  
 [<span data-ttu-id="1f17e-112">Crear procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="1f17e-112">Creating Extended Stored Procedures</span></span>](creating-extended-stored-procedures.md)  
  
  
