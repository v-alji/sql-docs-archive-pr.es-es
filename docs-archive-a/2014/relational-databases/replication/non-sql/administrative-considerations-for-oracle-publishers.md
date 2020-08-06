---
title: Consideraciones administrativas para los publicadores de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3104b507987a4a236d39dd0ae1f8e3c29358c730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675274"
---
# <a name="administrative-considerations-for-oracle-publishers"></a><span data-ttu-id="ced88-102">Consideraciones administrativas para los publicadores de Oracle</span><span class="sxs-lookup"><span data-stu-id="ced88-102">Administrative Considerations for Oracle Publishers</span></span>
  <span data-ttu-id="ced88-103">Después de configurar un publicador de Oracle y de implementar los mecanismos de seguimiento de cambios de la replicación, los administradores del sistema de bases de datos de Oracle pueden seguir utilizando las utilidades estándar de bases de datos de Oracle y realizar las tareas normales de administración del sistema.</span><span class="sxs-lookup"><span data-stu-id="ced88-103">After an Oracle Publisher is configured and the replication change tracking mechanisms are in place, administrators of the Oracle database system can still use standard Oracle database utilities and perform typical system administration tasks.</span></span> <span data-ttu-id="ced88-104">No obstante, debe tener en cuenta los efectos de ciertas tareas administrativas sobre los datos publicados.</span><span class="sxs-lookup"><span data-stu-id="ced88-104">However, you should be aware of the effects on the published data of performing certain administrative tasks.</span></span>  
  
 <span data-ttu-id="ced88-105">Excepto cuando se quita o se modifica una columna publicada para replicación, o cuando se quitan o se modifican objetos de replicación, estas consideraciones no se aplican a las publicaciones de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="ced88-105">With the exception of dropping or modifying a column that is published for replication, or dropping or modifying any replication objects, these considerations do not apply to snapshot publications.</span></span>  
  
## <a name="importing-and-loading-data"></a><span data-ttu-id="ced88-106">Importar y cargar datos</span><span class="sxs-lookup"><span data-stu-id="ced88-106">Importing and loading data</span></span>  
 <span data-ttu-id="ced88-107">Los desencadenadores se utilizan en el seguimiento de cambios para las publicaciones transaccionales en Oracle.</span><span class="sxs-lookup"><span data-stu-id="ced88-107">Triggers are used in change tracking for transactional publications on Oracle.</span></span> <span data-ttu-id="ced88-108">Los cambios en las tablas publicadas solo se pueden replicar en los suscriptores si los desencadenadores de la replicación se activan al producirse una actualización, una inserción o una eliminación.</span><span class="sxs-lookup"><span data-stu-id="ced88-108">Changes to published tables can be replicated to Subscribers only if the replication triggers fire when an update, insert, or delete occurs.</span></span> <span data-ttu-id="ced88-109">Las utilidades Oracle Import y SQL\*Loader de Oracle tienen opciones que determinan si un desencadenador se activará cuando se inserten filas en las tablas replicadas con estas utilidades.</span><span class="sxs-lookup"><span data-stu-id="ced88-109">The Oracle utilities Oracle Import and SQL\*Loader both have options that affect whether triggers will fire when rows are inserted into replicated tables with these utilities.</span></span>  
  
### <a name="oracle-import"></a><span data-ttu-id="ced88-110">Oracle Import</span><span class="sxs-lookup"><span data-stu-id="ced88-110">Oracle Import</span></span>  
 <span data-ttu-id="ced88-111">Con Oracle Import, puede establecer la opción **ignore** en 'y' o 'n' (el valor predeterminado es 'n').</span><span class="sxs-lookup"><span data-stu-id="ced88-111">With Oracle Import, you can set the option **ignore** to 'y' or 'n' (the default is 'n').</span></span> <span data-ttu-id="ced88-112">Si **ignore** se establece en 'n', la tabla se quita y se vuelve a crear durante la importación.</span><span class="sxs-lookup"><span data-stu-id="ced88-112">If **ignore** is set to 'n', the table is dropped and re-created during import.</span></span> <span data-ttu-id="ced88-113">Esto quita los desencadenadores de la replicación y deshabilita la replicación.</span><span class="sxs-lookup"><span data-stu-id="ced88-113">This removes replication triggers and disables replication.</span></span> <span data-ttu-id="ced88-114">Si **ignore** se establece en 'y', la importación intentará cargar las filas en la tabla existente, lo que activará los desencadenadores de la replicación.</span><span class="sxs-lookup"><span data-stu-id="ced88-114">If **ignore** is set to 'y', import will attempt to load the rows into the existing table, which fires the replication triggers.</span></span> <span data-ttu-id="ced88-115">Por lo tanto, asegúrese de que **ignore** esté establecido en 'y' al importar en una tabla replicada con la herramienta Import.</span><span class="sxs-lookup"><span data-stu-id="ced88-115">Therefore, ensure **ignore** is set to 'y' when importing into a replicated table with the Import tool.</span></span>  
  
### <a name="sqlloader"></a><span data-ttu-id="ced88-116">SQL\*Loader</span><span class="sxs-lookup"><span data-stu-id="ced88-116">SQL\*Loader</span></span>  
 <span data-ttu-id="ced88-117">Con SQL\*Loader, puede establecer la opción **direct** en "true" o "false" (el valor predeterminado es "false").</span><span class="sxs-lookup"><span data-stu-id="ced88-117">With SQL\*Loader, you can set the option **direct** to 'true' or 'false' (the default is 'false').</span></span> <span data-ttu-id="ced88-118">Si **direct** se establece en 'false', las filas se insertan por medio de instrucciones INSERT convencionales, que activan los disparadores de la replicación.</span><span class="sxs-lookup"><span data-stu-id="ced88-118">If **direct** is set to 'false', rows are inserted using conventional INSERT statements, which fire replication triggers.</span></span> <span data-ttu-id="ced88-119">Si **direct** se establece en 'true', se optimiza la carga y no se activan los desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="ced88-119">If **direct** is set to 'true', the load is optimized, and triggers are not fired.</span></span> <span data-ttu-id="ced88-120">Por lo tanto, asegúrese de que **direct** esté establecido en 'false' al cargar en una tabla replicada con la herramienta SQL\*Loader.</span><span class="sxs-lookup"><span data-stu-id="ced88-120">Therefore, ensure **direct** is set to 'false' when loading into a replicated table with the SQL\*Loader tool.</span></span>  
  
## <a name="making-changes-to-published-objects"></a><span data-ttu-id="ced88-121">Realizar cambios en objetos publicados</span><span class="sxs-lookup"><span data-stu-id="ced88-121">Making changes to published objects</span></span>  
 <span data-ttu-id="ced88-122">Las siguientes acciones no requieren ninguna consideración especial:</span><span class="sxs-lookup"><span data-stu-id="ced88-122">The following actions require no special considerations:</span></span>  
  
-   <span data-ttu-id="ced88-123">Volver a crear índices en tablas publicadas</span><span class="sxs-lookup"><span data-stu-id="ced88-123">Rebuilding indexes on published tables.</span></span>  
  
-   <span data-ttu-id="ced88-124">Agregar desencadenadores de usuario a una tabla publicada</span><span class="sxs-lookup"><span data-stu-id="ced88-124">Adding user triggers to a published table.</span></span>  
  
 <span data-ttu-id="ced88-125">La siguiente acción requiere que se detenga toda la actividad en las tablas publicadas:</span><span class="sxs-lookup"><span data-stu-id="ced88-125">The following action requires you to stop all activity on the published tables:</span></span>  
  
-   <span data-ttu-id="ced88-126">Mover una tabla publicada</span><span class="sxs-lookup"><span data-stu-id="ced88-126">Moving a published table.</span></span>  
  
 <span data-ttu-id="ced88-127">Las siguientes acciones requieren que se quite la publicación, se lleve a cabo la operación y después se vuelva a crear la publicación:</span><span class="sxs-lookup"><span data-stu-id="ced88-127">The following actions require you to drop the publication, perform the operation, and then recreate the publication:</span></span>  
  
-   <span data-ttu-id="ced88-128">Truncar una tabla publicada</span><span class="sxs-lookup"><span data-stu-id="ced88-128">Truncating a published table.</span></span>  
  
-   <span data-ttu-id="ced88-129">Cambiar el nombre de una tabla publicada</span><span class="sxs-lookup"><span data-stu-id="ced88-129">Renaming a published table.</span></span>  
  
-   <span data-ttu-id="ced88-130">Agregar una columna a una tabla publicada</span><span class="sxs-lookup"><span data-stu-id="ced88-130">Adding a column to a published table.</span></span>  
  
-   <span data-ttu-id="ced88-131">Quitar o modificar una columna publicada para replicación</span><span class="sxs-lookup"><span data-stu-id="ced88-131">Dropping or modifying a column that is published for replication.</span></span>  
  
-   <span data-ttu-id="ced88-132">Realizar operaciones no registradas</span><span class="sxs-lookup"><span data-stu-id="ced88-132">Performing non-logged operations.</span></span>  
  
## <a name="dropping-or-modifying-replication-objects"></a><span data-ttu-id="ced88-133">Quitar o modificar objetos de replicación</span><span class="sxs-lookup"><span data-stu-id="ced88-133">Dropping or modifying replication objects</span></span>  
 <span data-ttu-id="ced88-134">Debe quitar y volver a configurar el publicador si quita o modifica cualquier tabla de seguimiento, desencadenador, secuencia o procedimiento almacenado de nivel de publicador.</span><span class="sxs-lookup"><span data-stu-id="ced88-134">You must drop and reconfigure the Publisher if you drop or modify any Publisher level tracking tables, triggers, sequences, or stored procedures.</span></span> <span data-ttu-id="ced88-135">Para obtener una lista parcial de estos objetos, consulte [Objetos creados en el publicador de Oracle](objects-created-on-the-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="ced88-135">For a partial list of these objects, see [Objects Created on the Oracle Publisher](objects-created-on-the-oracle-publisher.md).</span></span>  
  
 <span data-ttu-id="ced88-136">Para obtener información acerca de cómo quitar y volver a configurar el publicador, vea la sección sobre la realización de cambios que requieren volver a configurar el publicador en el tema [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="ced88-136">For information about dropping and reconfiguring the Publisher, see the section "Changes are made that require reconfiguration of the Publisher" in the topic [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced88-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ced88-137">See Also</span></span>  
 <span data-ttu-id="ced88-138">[Configurar un publicador de Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="ced88-138">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="ced88-139">[Consideraciones y limitaciones de diseño de los publicadores de Oracle](design-considerations-and-limitations-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="ced88-139">[Design Considerations and Limitations for Oracle Publishers](design-considerations-and-limitations-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="ced88-140">Información general de la publicación de Oracle</span><span class="sxs-lookup"><span data-stu-id="ced88-140">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
