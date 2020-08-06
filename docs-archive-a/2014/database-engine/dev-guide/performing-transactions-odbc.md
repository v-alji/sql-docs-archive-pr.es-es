---
title: Realizar transacciones (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: f431191a-5762-4f0b-85bb-ac99aff29724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8abc09c9395225dd653a072fd6c25dadce0849b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750134"
---
# <a name="performing-transactions-odbc"></a><span data-ttu-id="12699-102">Realizar transacciones (ODBC)</span><span class="sxs-lookup"><span data-stu-id="12699-102">Performing Transactions (ODBC)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="12699-103">y el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client admiten las funciones de administración de transacciones de la API de ODBC.</span><span class="sxs-lookup"><span data-stu-id="12699-103">and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver support the ODBC API transaction management functions.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="12699-104">proporciona compatibilidad completa para realizar transacciones locales en un servidor individual.</span><span class="sxs-lookup"><span data-stu-id="12699-104">offers full support for local transactions on an individual server.</span></span> <span data-ttu-id="12699-105">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utiliza estas características para admitir las funciones de la API de ODBC que administran las transacciones.</span><span class="sxs-lookup"><span data-stu-id="12699-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses these features to support the ODBC API functions that manage transactions.</span></span>  
  
 <span data-ttu-id="12699-106">Mediante el uso de Microsoft DTC (Coordinador de transacciones distribuidas), el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client puede participar en transacciones distribuidas que se realizan en varios servidores.</span><span class="sxs-lookup"><span data-stu-id="12699-106">Through the use of the Microsoft Distributed Transaction Coordinator (MS DTC), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver can participate in distributed transactions spanning multiple servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12699-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12699-107">In This Section</span></span>  
  
-   [<span data-ttu-id="12699-108">Transacciones en ODBC</span><span class="sxs-lookup"><span data-stu-id="12699-108">Transactions in ODBC</span></span>](../../relational-databases/native-client/odbc/performing-transactions-in-odbc.md)  
  
-   [<span data-ttu-id="12699-109">Realizar transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="12699-109">Performing Distributed Transactions</span></span>](../../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
