---
title: ICommand (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ICommand [SQL Server Native Client]
ms.assetid: 5e24b3a0-0658-44fc-b653-f4c52f9eb328
author: rothja
ms.author: jroth
ms.openlocfilehash: 03bdccc83a04078210f2283d0b330f237ed02979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676489"
---
# <a name="icommand-ole-db"></a><span data-ttu-id="bba19-102">ICommand (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="bba19-102">ICommand (OLE DB)</span></span>
  <span data-ttu-id="bba19-103">Este tema trata el comportamiento de OLE DB que es específico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="bba19-103">This topic discusses OLE DB behavior that is specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="icommandexecute"></a><span data-ttu-id="bba19-104">ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="bba19-104">ICommand::Execute</span></span>  
 <span data-ttu-id="bba19-105">Insertar datos que sean mayores que el tamaño de una columna suele producir un error.</span><span class="sxs-lookup"><span data-stu-id="bba19-105">Inserting data that is greater than the size of a column typically results in an error.</span></span> <span data-ttu-id="bba19-106">Sin embargo, hay situaciones en las que se devolverá S_OK pero *dwStatus* se configurará en DBSTATUS_S_TRUNCATED.</span><span class="sxs-lookup"><span data-stu-id="bba19-106">However, there are situations where S_OK will be returned but the *dwStatus* will be set to DBSTATUS_S_TRUNCATED.</span></span> <span data-ttu-id="bba19-107">Esto se suele producir al insertar datos con parámetros, donde la columna no es lo bastante grande para contener los datos y no se ha llamado a `ICommandWithParameters::SetParameterInfo`.</span><span class="sxs-lookup"><span data-stu-id="bba19-107">This generally occurs when inserting data with parameters, where the column is not large enough to hold the data, and `ICommandWithParameters::SetParameterInfo` has not been called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba19-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bba19-108">See Also</span></span>  
 [<span data-ttu-id="bba19-109">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="bba19-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
