---
title: Opciones de validación de suscripciones (suscripciones transaccionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 40a617dd1beff24f8f072f5d139bec7c1ca65f33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750653"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a><span data-ttu-id="82660-102">Opciones de validación de suscripciones (suscripciones transaccionales)</span><span class="sxs-lookup"><span data-stu-id="82660-102">Subscription Validation Options (Transactional Subscriptions)</span></span>
  <span data-ttu-id="82660-103">Utilice el cuadro de diálogo **Opciones de validación de suscripciones** para especificar si la validación debe utilizar solo un recuento de filas o un recuento de filas y una suma de comprobación binaria.</span><span class="sxs-lookup"><span data-stu-id="82660-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only, or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="82660-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="82660-104">Options</span></span>  
 <span data-ttu-id="82660-105">**Comprobar que el suscriptor tiene el mismo número de filas de datos replicados que el publicador**</span><span class="sxs-lookup"><span data-stu-id="82660-105">**Verify that the Subscriber has the same number of rows of replicated data as the Publisher**</span></span>  
 <span data-ttu-id="82660-106">Seleccione el tipo de validación de número de fila que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="82660-106">Select the type of row count validation to perform.</span></span> <span data-ttu-id="82660-107">Para publicaciones de Oracle, la única opción disponible es **Calcular un recuento de filas real consultando las tablas directamente**.</span><span class="sxs-lookup"><span data-stu-id="82660-107">For Oracle publications, the only available option is **Compute an actual row count by querying the tables directly**.</span></span>  
  
 <span data-ttu-id="82660-108">**Comparar las sumas de comprobación para comprobar los datos de las filas**</span><span class="sxs-lookup"><span data-stu-id="82660-108">**Compare checksums to verify row data**</span></span>  
 <span data-ttu-id="82660-109">Además de llevar a cabo un recuento de filas en el publicador y en el suscriptor, se calcula una suma de comprobación de todos los datos utilizando el algoritmo binario de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="82660-109">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="82660-110">Si el número de filas da un error, no se lleva a cabo la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="82660-110">If the row count fails, the checksum is not performed.</span></span>  
  
 <span data-ttu-id="82660-111">**Detener el Agente de distribución después de finalizar la validación**</span><span class="sxs-lookup"><span data-stu-id="82660-111">**Stop the Distribution Agent after the validation has completed**</span></span>  
 <span data-ttu-id="82660-112">De forma predeterminada, el Agente de distribución se ejecuta sin interrupción.</span><span class="sxs-lookup"><span data-stu-id="82660-112">By default, the Distribution Agent runs continuously.</span></span> <span data-ttu-id="82660-113">Seleccione esta opción para detener el agente una vez realizada la validación.</span><span class="sxs-lookup"><span data-stu-id="82660-113">Select this option to stop the agent after validation is performed.</span></span> <span data-ttu-id="82660-114">Esto permite comprobar si la validación ha sido correcta antes de continuar replicando datos en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="82660-114">This allows you to check whether validation was successful before continuing to replicate data to the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82660-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82660-115">See Also</span></span>  
 <span data-ttu-id="82660-116">[Validar datos en el suscriptor](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="82660-116">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="82660-117">Validar datos replicados</span><span class="sxs-lookup"><span data-stu-id="82660-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
