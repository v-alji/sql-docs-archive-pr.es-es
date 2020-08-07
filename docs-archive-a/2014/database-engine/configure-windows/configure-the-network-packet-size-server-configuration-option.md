---
title: Establecer la opción de configuración del servidor Tamaño de paquete de red | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default packet size
- size [SQL Server], packets
- packets [SQL Server], size
- network packet size option
ms.assetid: 236985bf-fc4a-4a57-98f7-a71ef977fd7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69e5963675349bceff6a0ee022f6dc28da03db59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745965"
---
# <a name="configure-the-network-packet-size-server-configuration-option"></a><span data-ttu-id="bb944-102">Establecer la opción de configuración del servidor Tamaño de paquete de red</span><span class="sxs-lookup"><span data-stu-id="bb944-102">Configure the network packet size Server Configuration Option</span></span>
  <span data-ttu-id="bb944-103">En este tema se describe cómo configurar la `network packet size` opción de configuración del servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb944-103">This topic describes how to configure the `network packet size` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bb944-104">La `network packet size` opción establece el tamaño de paquete (en bytes) que se usa en toda la red.</span><span class="sxs-lookup"><span data-stu-id="bb944-104">The `network packet size` option sets the packet size (in bytes) that is used across the whole network.</span></span> <span data-ttu-id="bb944-105">Los paquetes son fragmentos de datos de tamaño fijo que transfieren solicitudes y resultados entre clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="bb944-105">Packets are the fixed-size chunks of data that transfer requests and results between clients and servers.</span></span> <span data-ttu-id="bb944-106">El tamaño predeterminado de los paquetes es de 4096 bytes.</span><span class="sxs-lookup"><span data-stu-id="bb944-106">The default packet size is 4,096 bytes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb944-107">No cambie el tamaño de los paquetes a menos que esté seguro de que mejorará el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bb944-107">Do not change the packet size unless you are certain that it will improve performance.</span></span> <span data-ttu-id="bb944-108">En la mayoría de las aplicaciones, el tamaño más conveniente de los paquetes es el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bb944-108">For most applications, the default packet size is best.</span></span>  
  
 <span data-ttu-id="bb944-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="bb944-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bb944-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="bb944-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bb944-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="bb944-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bb944-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="bb944-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="bb944-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="bb944-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bb944-114">**Para configurar la opción de tamaño de paquete de red, use:**</span><span class="sxs-lookup"><span data-stu-id="bb944-114">**To configure the network packet size option, using:**</span></span>  
  
     [<span data-ttu-id="bb944-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb944-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bb944-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb944-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="bb944-117">**Seguimiento:**  [Después de configurar la opción de tamaño de paquete de red](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bb944-117">**Follow Up:**  [After you configure the network packet size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bb944-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="bb944-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bb944-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="bb944-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bb944-120">El tamaño de paquete de red máximo para las conexiones cifradas es de 16.383 bytes.</span><span class="sxs-lookup"><span data-stu-id="bb944-120">The maximum network packet size for encrypted connections is 16,383 bytes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="bb944-121">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="bb944-121">Recommendations</span></span>  
  
-   <span data-ttu-id="bb944-122">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="bb944-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="bb944-123">Si una aplicación realiza operaciones de copia masiva, o bien envía o recibe una gran cantidad de datos de texto o imagen, el uso de paquetes de un tamaño superior al predeterminado podría mejorar la eficacia, ya que tiene como resultado un número menor de operaciones de lectura y escritura en la red.</span><span class="sxs-lookup"><span data-stu-id="bb944-123">If an application does bulk copy operations or sends or receives large amounts of text or image data, a packet size larger than the default might improve efficiency because it results in fewer network read-and-write operations.</span></span> <span data-ttu-id="bb944-124">Si una aplicación envía y recibe pequeñas cantidades de información, puede establecer un tamaño de 512 bytes para cada paquete, lo que es suficiente para la mayor parte de las transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="bb944-124">If an application sends and receives small amounts of information, the packet size can be set to 512 bytes, which is sufficient for most data transfers.</span></span>  
  
-   <span data-ttu-id="bb944-125">En sistemas que usen diferentes protocolos de red, establezca el tamaño de paquete de red en el tamaño para el protocolo más usado.</span><span class="sxs-lookup"><span data-stu-id="bb944-125">On systems that are using different network protocols, set network packet size to the size for the most common protocol used.</span></span> <span data-ttu-id="bb944-126">La opción network packet size mejora el rendimiento de la red cuando los protocolos de red admiten paquetes más grandes.</span><span class="sxs-lookup"><span data-stu-id="bb944-126">The network packet size option improves network performance when network protocols support larger packets.</span></span> <span data-ttu-id="bb944-127">Las aplicaciones cliente pueden suplantar este valor.</span><span class="sxs-lookup"><span data-stu-id="bb944-127">Client applications can override this value.</span></span>  
  
-   <span data-ttu-id="bb944-128">También puede llamar a funciones de OLE DB, Conectividad abierta de bases de datos (ODBC) y DB-Library para solicitar un cambio del tamaño de los paquetes.</span><span class="sxs-lookup"><span data-stu-id="bb944-128">You can also call OLE DB, Open Database Connectivity (ODBC), and DB-Library functions request a change the packet size.</span></span> <span data-ttu-id="bb944-129">Si el servidor no puede admitir el tamaño del paquete solicitado, [!INCLUDE[ssDE](../../includes/ssde-md.md)] enviará un mensaje de advertencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="bb944-129">If the server cannot support the requested packet size, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will send a warning message to the client.</span></span> <span data-ttu-id="bb944-130">En algunos casos, el cambio del tamaño del paquete podría crear un error del vínculo de comunicación como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb944-130">In some circumstances, changing the packet size might lead to a communication link failure, such as the following:</span></span>  
  
     `Native Error: 233, no process is on the other end of the pipe.`  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bb944-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="bb944-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bb944-132">Permisos</span><span class="sxs-lookup"><span data-stu-id="bb944-132">Permissions</span></span>  
 <span data-ttu-id="bb944-133">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="bb944-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="bb944-134">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bb944-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="bb944-135">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="bb944-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bb944-136">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb944-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="bb944-137">Para configurar la opción de tamaño de paquete de red</span><span class="sxs-lookup"><span data-stu-id="bb944-137">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="bb944-138">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb944-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="bb944-139">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="bb944-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="bb944-140">En **Red**, seleccione un valor para el cuadro **Tamaño de paquete de red** .</span><span class="sxs-lookup"><span data-stu-id="bb944-140">Under **Network**, select a value for the **Network Packet Size** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bb944-141">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb944-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="bb944-142">Para configurar la opción de tamaño de paquete de red</span><span class="sxs-lookup"><span data-stu-id="bb944-142">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="bb944-143">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb944-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bb944-144">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="bb944-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bb944-145">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb944-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bb944-146">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `network packet size` en `6500` bytes.</span><span class="sxs-lookup"><span data-stu-id="bb944-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `network packet size` option to `6500` bytes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'network packet size', 6500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="bb944-147">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb944-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-network-packet-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="bb944-148">Seguimiento: Después de configurar la opción de tamaño de paquete de red</span><span class="sxs-lookup"><span data-stu-id="bb944-148">Follow Up: After you configure the network packet size option</span></span>  
 <span data-ttu-id="bb944-149">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="bb944-149">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb944-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb944-150">See Also</span></span>  
 <span data-ttu-id="bb944-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bb944-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="bb944-152">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bb944-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="bb944-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bb944-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
