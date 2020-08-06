---
title: Opciones de validación de suscripciones (Suscripciones de mezcla) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.mergeoptions.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: 4958c4ab-2025-42ce-b836-6fb4e9e6f24d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 458da0387dbaa1b366348c374748c42946893feb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750657"
---
# <a name="subscription-validation-options-merge-subscriptions"></a><span data-ttu-id="8ebc4-102">Opciones de validación de suscripciones (Suscripciones de mezcla)</span><span class="sxs-lookup"><span data-stu-id="8ebc4-102">Subscription Validation Options (Merge Subscriptions)</span></span>
  <span data-ttu-id="8ebc4-103">Use el cuadro de diálogo **Opciones de validación de suscripciones** para especificar si la validación debe utilizar solamente recuento de filas o recuento de filas y suma de comprobación binaria.</span><span class="sxs-lookup"><span data-stu-id="8ebc4-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8ebc4-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="8ebc4-104">Options</span></span>  
 <span data-ttu-id="8ebc4-105">**Solo comprobar recuentos de filas**</span><span class="sxs-lookup"><span data-stu-id="8ebc4-105">**Verify the row counts only**</span></span>  
 <span data-ttu-id="8ebc4-106">Seleccione esta opción para validar si la tabla del suscriptor tiene el mismo número de filas que la tabla del publicador.</span><span class="sxs-lookup"><span data-stu-id="8ebc4-106">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="8ebc4-107">Este método no valida si el contenido de las filas coincide.</span><span class="sxs-lookup"><span data-stu-id="8ebc4-107">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="8ebc4-108">La validación del recuento de filas proporciona una idea sobre validación que puede ponerle al corriente de problemas con los datos.</span><span class="sxs-lookup"><span data-stu-id="8ebc4-108">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="8ebc4-109">**Comprobar los recuentos de filas y comparar las sumas de comprobación para comprobar los datos de las filas**</span><span class="sxs-lookup"><span data-stu-id="8ebc4-109">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="8ebc4-110">Además de llevar a cabo un recuento de filas en el publicador y en el suscriptor, se calcula una suma de comprobación de todos los datos utilizando el algoritmo binario de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8ebc4-110">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="8ebc4-111">Si el número de filas da un error, no se lleva a cabo la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8ebc4-111">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="8ebc4-112">Esta opción no es válida para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ebc4-112">This option is not valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebc4-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ebc4-113">See Also</span></span>  
 <span data-ttu-id="8ebc4-114">[Validar datos en el suscriptor](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="8ebc4-114">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="8ebc4-115">Validar datos replicados</span><span class="sxs-lookup"><span data-stu-id="8ebc4-115">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
