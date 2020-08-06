---
title: Claves simétricas en bases de datos de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ca0fb62ccb32ce244e1087281997dcd9929df89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670994"
---
# <a name="symmetric-keys-on-user-databases"></a><span data-ttu-id="b1ad5-102">Claves simétricas en bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="b1ad5-102">Symmetric Keys on User Databases</span></span>
  <span data-ttu-id="b1ad5-103">Esta regla comprueba si las claves que tienen una longitud de menos de 128 bytes no utilizan el algoritmo de cifrado RC2 o RC4.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-103">This rule checks whether keys that have a length of less than 128 bytes do not use the RC2 or RC4 encryption algorithm.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b1ad5-104">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="b1ad5-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b1ad5-105">Utilice AES de 128 bits o más para crear las claves simétricas para el cifrado de los datos.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-105">Use AES 128 bit or larger to create symmetric keys for data encryption.</span></span> <span data-ttu-id="b1ad5-106">Si el sistema operativo no admite AES, utilice 3DES.</span><span class="sxs-lookup"><span data-stu-id="b1ad5-106">If AES is not supported by your operating system, use 3DES.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b1ad5-107">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="b1ad5-107">For More Information</span></span>  
 [<span data-ttu-id="b1ad5-108">Elegir un algoritmo de cifrado</span><span class="sxs-lookup"><span data-stu-id="b1ad5-108">Choose an Encryption Algorithm</span></span>](../security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1ad5-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1ad5-109">See Also</span></span>  
 [<span data-ttu-id="b1ad5-110">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="b1ad5-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
