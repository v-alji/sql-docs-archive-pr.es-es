---
title: Configurar el trabajo del conjunto de transacciones para un publicador de Oracle (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_publisherproperty
- Oracle publishing [SQL Server replication], configuring
ms.assetid: beea1a5c-0053-4971-a68f-0da53063fcbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a25ce755a505f0efd7c25243b8969a962ea701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750789"
---
# <a name="configure-the-transaction-set-job-for-an-oracle-publisher-replication-transact-sql-programming"></a><span data-ttu-id="edc39-102">Configurar el trabajo del conjunto de transacciones para un publicador de Oracle (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="edc39-102">Configure the Transaction Set Job for an Oracle Publisher (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="edc39-103">El trabajo **Xactset** es un trabajo de base de datos de Oracle creado por replicación que se ejecuta en un publicador de Oracle para crear conjuntos de transacciones cuando el agente de registro del LOG no está conectado al publicador.</span><span class="sxs-lookup"><span data-stu-id="edc39-103">The **Xactset** job is an Oracle database job created by replication that runs at an Oracle Publisher to create transaction sets when the Log Reader Agent is not connected to the Publisher.</span></span> <span data-ttu-id="edc39-104">Puede habilitar y configurar este trabajo desde el distribuidor mediante programación con procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="edc39-104">You can enable and configure this job from the Distributor programmatically using replication stored procedures.</span></span> <span data-ttu-id="edc39-105">Para obtener más información, consulte [Optimizar el rendimiento de publicadores de Oracle](../non-sql/performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="edc39-105">For more information, see [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span></span>  
  
### <a name="to-enable-the-transaction-set-job"></a><span data-ttu-id="edc39-106">Para habilitar el trabajo del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="edc39-106">To enable the transaction set job</span></span>  
  
1.  <span data-ttu-id="edc39-107">En el publicador de Oracle, establezca el parámetro de inicialización **job_queue_processes** en un valor suficiente para permitir la ejecución del trabajo Xactset.</span><span class="sxs-lookup"><span data-stu-id="edc39-107">At the Oracle Publisher, set the **job_queue_processes** initialization parameter to a sufficient value to allow the Xactset job run.</span></span> <span data-ttu-id="edc39-108">Para obtener más información acerca de este parámetro, vea la documentación de la base de datos del publicador de Oracle.</span><span class="sxs-lookup"><span data-stu-id="edc39-108">For more information about this parameter, see the database documentation for the Oracle Publisher.</span></span>  
  
2.  <span data-ttu-id="edc39-109">En el distribuidor, ejecute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-109">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="edc39-110">Especifique el nombre del publicador de Oracle para el \*\* \@ publicador**, un valor de `xactsetbatching` para \*\* \@ PropertyName**y un valor de `enabled` para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="edc39-110">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetbatching` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="edc39-111">En el distribuidor, ejecute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-111">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="edc39-112">Especifique el nombre del publicador de Oracle para el \*\* \@ publicador**, un valor de `xactsetjobinterval` para \*\* \@ PropertyName**y el intervalo del trabajo, en minutos, para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="edc39-112">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjobinterval` for **\@propertyname**, and the job interval, in minutes, for **\@propertyvalue**.</span></span>  
  
4.  <span data-ttu-id="edc39-113">En el distribuidor, ejecute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-113">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="edc39-114">Especifique el nombre del publicador de Oracle para el \*\* \@ publicador**, un valor de `xactsetjob` para \*\* \@ PropertyName**y un valor de `enabled` para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="edc39-114">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
### <a name="to-configure-the-transaction-set-job"></a><span data-ttu-id="edc39-115">Para configurar el trabajo del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="edc39-115">To configure the transaction set job</span></span>  
  
1.  <span data-ttu-id="edc39-116">(Opcional) En el distribuidor, ejecute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-116">(Optional) At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="edc39-117">Especifique el nombre del publicador de Oracle en **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="edc39-117">Specify the name of the Oracle Publisher for **\@publisher**.</span></span> <span data-ttu-id="edc39-118">De esta forma se devuelven las propiedades del trabajo **Xactset** al publicador.</span><span class="sxs-lookup"><span data-stu-id="edc39-118">This returns properties of the **Xactset** job at the Publisher.</span></span>  
  
2.  <span data-ttu-id="edc39-119">En el distribuidor, ejecute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-119">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="edc39-120">Especifique el nombre del publicador de Oracle para el \*\* \@ publicador**, el nombre de la propiedad del trabajo Xactset que se establece para \*\* \@ PropertyName**y la nueva configuración para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="edc39-120">Specify the name of the Oracle Publisher for **\@publisher**, the name of the Xactset job property being set for **\@propertyname**, and new setting for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="edc39-121">(Opcional) Repita el paso 2 para cada propiedad del trabajo Xactset que se establece.</span><span class="sxs-lookup"><span data-stu-id="edc39-121">(Optional) Repeat step 2 for each Xactset job property being set.</span></span> <span data-ttu-id="edc39-122">Al cambiar la `xactsetjobinterval` propiedad, debe reiniciar el trabajo en el publicador de Oracle para que el nuevo intervalo surta efecto.</span><span class="sxs-lookup"><span data-stu-id="edc39-122">When changing the `xactsetjobinterval` property, you must restart the job on the Oracle Publisher for the new interval to take effect.</span></span>  
  
### <a name="to-view-properties-of-the-transaction-set-job"></a><span data-ttu-id="edc39-123">Para ver las propiedades del trabajo del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="edc39-123">To view properties of the transaction set job</span></span>  
  
1.  <span data-ttu-id="edc39-124">En el distribuidor, ejecute [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-124">At the Distributor, execute [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span></span> <span data-ttu-id="edc39-125">Especifique el nombre del publicador de Oracle en **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="edc39-125">Specify the name of the Oracle Publisher for **\@publisher**.</span></span>  
  
### <a name="to-disable-the-transaction-set-job"></a><span data-ttu-id="edc39-126">Para deshabilitar el trabajo del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="edc39-126">To disable the transaction set job</span></span>  
  
1.  <span data-ttu-id="edc39-127">En el distribuidor, ejecute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edc39-127">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="edc39-128">Especifique el nombre del publicador de Oracle para el \*\* \@ publicador**, un valor de `xactsetjob` para \*\* \@ PropertyName**y un valor de `disabled` para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="edc39-128">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `disabled` for **\@propertyvalue**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edc39-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edc39-129">Example</span></span>  
 <span data-ttu-id="edc39-130">El ejemplo siguiente habilita el trabajo `Xactset` y establece un intervalo de tres minutos entre ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="edc39-130">The following example enables the `Xactset` job and sets an interval of three minutes between runs.</span></span>  
  
 [!code-sql[HowTo#sp_enable_xactsetjob](../../../snippets/tsql/SQL15/replication/howto/tsql/enablexactsetjob.sql#sp_enable_xactsetjob)]  
  
## <a name="see-also"></a><span data-ttu-id="edc39-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edc39-131">See Also</span></span>  
 <span data-ttu-id="edc39-132">[Optimización del rendimiento para publicadores de Oracle](../non-sql/performance-tuning-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="edc39-132">[Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="edc39-133">Conceptos de procedimientos almacenados del sistema de replicación</span><span class="sxs-lookup"><span data-stu-id="edc39-133">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
