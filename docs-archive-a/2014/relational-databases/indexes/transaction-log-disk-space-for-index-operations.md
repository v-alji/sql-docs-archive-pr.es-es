---
title: Espacio en disco del registro de transacciones para operaciones de índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index disk space [SQL Server]
- space [SQL Server], indexes
- transaction logs [SQL Server], disk space
- disk space [SQL Server], transaction logs
- space [SQL Server], transaction logs
ms.assetid: 4f8a4922-4507-4072-be67-c690528d5c3b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c34c9ff7a9494496d6c60d5920184c0ce86131d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749301"
---
# <a name="transaction-log-disk-space-for-index-operations"></a><span data-ttu-id="238a9-102">Espacio en disco del registro de transacciones para operaciones de índice</span><span class="sxs-lookup"><span data-stu-id="238a9-102">Transaction Log Disk Space for Index Operations</span></span>
  <span data-ttu-id="238a9-103">Las operaciones de índice a gran escala pueden generar cargas grandes de datos que podrían llenar rápidamente el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="238a9-103">Large-scale index operations can generate large data loads that can cause the transaction log to fill quickly.</span></span> <span data-ttu-id="238a9-104">Para estar seguros de que la operación de índice se pueda revertir, el registro de transacciones no se puede truncar hasta que se haya completado la operación de índice; no obstante, se puede realizar una copia de seguridad del registro durante la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="238a9-104">To make sure that the index operation can be rolled back, the transaction log cannot be truncated until the index operation has completed; however, the log can be backed up during the index operation.</span></span> <span data-ttu-id="238a9-105">Por lo tanto, el registro de transacciones debe tener suficiente espacio para almacenar las transacciones de la operación de índice y cualquier transacción de usuario simultánea durante la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="238a9-105">Therefore, the transaction log must have sufficient room to store both the index operation transactions and any concurrent user transactions for the duration of the index operation.</span></span> <span data-ttu-id="238a9-106">Esto se cumple para las operaciones de índice en línea y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="238a9-106">This is true for both offline and online index operations.</span></span> <span data-ttu-id="238a9-107">Debido a que no es posible obtener acceso a las tablas subyacentes durante una operación de índice sin conexión, puede que haya pocas transacciones de usuario y el registro no crezca tan rápidamente.</span><span class="sxs-lookup"><span data-stu-id="238a9-107">Because the underlying tables cannot be accessed during an offline index operation, there may be few user transactions and the log may not grow as quickly.</span></span> <span data-ttu-id="238a9-108">Las operaciones de índice en línea no impiden la actividad simultánea de usuarios, por lo tanto, las operaciones de índice en línea a gran escala junto con un número significativo de transacciones simultáneas pueden provocar el crecimiento continuo del registro de transacciones sin la posibilidad de truncar el registro.</span><span class="sxs-lookup"><span data-stu-id="238a9-108">Online index operations do not prevent concurrent user activity, therefore, large-scale online index operations combined with significant concurrent user transactions can cause continuous growth of the transaction log without an option to truncate the log.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="238a9-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="238a9-109">Recommendations</span></span>  
 <span data-ttu-id="238a9-110">Cuando ejecute operaciones de índice a gran escala, tenga en cuentas las siguientes recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="238a9-110">When you run large-scale index operations, consider the following recommendations:</span></span>  
  
1.  <span data-ttu-id="238a9-111">Compruebe que se ha realizado una copia de seguridad del registro de transacciones y que éste se ha truncado antes de ejecutar operaciones de índice a gran escala en línea, así como que el registro dispone de espacio suficiente para almacenar el índice proyectado y las transacciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="238a9-111">Make sure the transaction log has been backed up and truncated before running large-scale index operations online, and that the log has sufficient space to store the projected index and user transactions.</span></span>  
  
2.  <span data-ttu-id="238a9-112">Considere la posibilidad de establecer la opción SORT_IN_TEMPDB en ON para la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="238a9-112">Consider setting the SORT_IN_TEMPDB option to ON for the index operation.</span></span> <span data-ttu-id="238a9-113">De este modo, se separan las transacciones de índice de transacciones de usuario simultáneas.</span><span class="sxs-lookup"><span data-stu-id="238a9-113">This separates the index transactions from the concurrent user transactions.</span></span> <span data-ttu-id="238a9-114">Las transacciones de índice se almacenarán en el registro de transacciones de **tempdb** y las transacciones de usuario simultáneas se almacenarán en el registro de transacciones de la base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="238a9-114">The index transactions will be stored in the **tempdb** transaction log, and the concurrent user transactions will be stored in the transaction log of the user database.</span></span> <span data-ttu-id="238a9-115">Esto permite que el registro de transacciones de la base de datos de usuario se trunque durante la operación de índice si es necesario.</span><span class="sxs-lookup"><span data-stu-id="238a9-115">This allows for the transaction log of the user database to be truncated during the index operation if it is required.</span></span> <span data-ttu-id="238a9-116">Además, si el registro de **tempdb** no se encuentra en el mismo disco que el registro de la base de datos de usuario, los dos registros no compiten por el mismo espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="238a9-116">Additionally, if the **tempdb** log is not on the same disk as the user database log, the two logs are not competing for the same disk space.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="238a9-117">Compruebe que la base de datos **tempdb** y el registro de transacciones disponen de espacio suficiente para controlar la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="238a9-117">Verify that the **tempdb** database and transaction log have sufficient disk space to handle the index operation.</span></span> <span data-ttu-id="238a9-118">El registro de transacciones de **tempdb** no se puede truncar hasta que finalice la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="238a9-118">The **tempdb** transaction log cannot be truncated until the index operation is completed.</span></span>  
  
3.  <span data-ttu-id="238a9-119">Utilice un modelo de recuperación de base de datos que permita el registro mínimo de la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="238a9-119">Use a database recovery model that allows for minimal logging of the index operation.</span></span> <span data-ttu-id="238a9-120">Esto puede reducir el tamaño del registro e impide que el registro llene el espacio de registro.</span><span class="sxs-lookup"><span data-stu-id="238a9-120">This may reduce the size of the log and prevent the log from filling the log space.</span></span>  
  
4.  <span data-ttu-id="238a9-121">No ejecute la operación de índice en línea en una transacción explícita.</span><span class="sxs-lookup"><span data-stu-id="238a9-121">Do not run the online index operation in an explicit transaction.</span></span> <span data-ttu-id="238a9-122">El registro no se truncará hasta que finalice la operación explícita.</span><span class="sxs-lookup"><span data-stu-id="238a9-122">The log will not be truncated until the explicit transaction ends.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="238a9-123">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="238a9-123">Related Content</span></span>  
 [<span data-ttu-id="238a9-124">Requisitos de espacio en disco para operaciones DDL de índice</span><span class="sxs-lookup"><span data-stu-id="238a9-124">Disk Space Requirements for Index DDL Operations</span></span>](disk-space-requirements-for-index-ddl-operations.md)  
  
 [<span data-ttu-id="238a9-125">Ejemplo de espacio en disco del índice</span><span class="sxs-lookup"><span data-stu-id="238a9-125">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
  
