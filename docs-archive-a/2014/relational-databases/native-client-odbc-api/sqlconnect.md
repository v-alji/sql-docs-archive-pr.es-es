---
title: SQLConnect | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLConnect function
ms.assetid: 6da74e3a-4388-4907-81cb-987389bae467
author: rothja
ms.author: jroth
ms.openlocfilehash: 43b37ae16638e461e37edaead83cd9ceedc1c86d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672956"
---
# <a name="sqlconnect"></a><span data-ttu-id="cdb81-102">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="cdb81-102">SQLConnect</span></span>
  <span data-ttu-id="cdb81-103">Cuando se abre una conexión, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client establece SQL_COPT_SS_MUTUALLY_AUTHENTICATED y SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD en el método de autenticación que se utiliza para abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="cdb81-103">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span> <span data-ttu-id="cdb81-104">Para obtener más información acerca de los SPN, consulte [nombres de entidad de seguridad de servicio &#40;spn&#41; en conexiones de cliente &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cdb81-104">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="sqlconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="cdb81-105">Compatibilidad de SQLConnect para la alta disponibilidad con recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="cdb81-105">SQLConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="cdb81-106">Para obtener más información sobre el uso de **SQLConnect** para conectarse a un [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] clúster, consulte [SQL Server Native Client compatibilidad con la alta disponibilidad y la recuperación ante desastres](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="cdb81-106">For more information on using **SQLConnect** to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb81-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cdb81-107">See Also</span></span>  
 <span data-ttu-id="cdb81-108">[SQLConnect función)](https://go.microsoft.com/fwlink/?LinkId=101541) </span><span class="sxs-lookup"><span data-stu-id="cdb81-108">[SQLConnect Function](https://go.microsoft.com/fwlink/?LinkId=101541) </span></span>  
 [<span data-ttu-id="cdb81-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="cdb81-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
