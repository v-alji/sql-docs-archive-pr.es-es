---
title: Conexión al servidor (Oracle) y propiedades de conexión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c76a3058283a098357701a44de48efff917acd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662841"
---
# <a name="connect-to-server-oracle-connection-properties"></a><span data-ttu-id="c282c-102">Conectar al servidor (Oracle), Propiedades de conexión</span><span class="sxs-lookup"><span data-stu-id="c282c-102">Connect to Server (Oracle), Connection Properties</span></span>
  <span data-ttu-id="c282c-103">Utilice la pestaña **Propiedades de conexión** del cuadro de diálogo **Conectar al servidor** para especificar una opción de publicación de **Puerta de enlace** o **Completo**.</span><span class="sxs-lookup"><span data-stu-id="c282c-103">Use the **Connection Properties** tab of the **Connect to Server** dialog box to specify a publishing option of **Gateway** or **Complete**.</span></span> <span data-ttu-id="c282c-104">Después de identificar un publicador, esta opción no se puede cambiar sin quitar y volver a configurar el publicador.</span><span class="sxs-lookup"><span data-stu-id="c282c-104">After a Publisher is identified, this option cannot be changed without dropping and reconfiguring the Publisher.</span></span> <span data-ttu-id="c282c-105">Para obtener más información, vea [Configurar un publicador de Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="c282c-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c282c-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="c282c-106">Options</span></span>  
 <span data-ttu-id="c282c-107">**Tipo de anunciante**</span><span class="sxs-lookup"><span data-stu-id="c282c-107">**Publisher type**</span></span>  
 <span data-ttu-id="c282c-108">Seleccione **Puerta de enlace** o **Completo**.</span><span class="sxs-lookup"><span data-stu-id="c282c-108">Select **Gateway** or **Complete**.</span></span> <span data-ttu-id="c282c-109">La opción **Completo** está diseñada para proporcionar publicaciones de instantáneas y transaccionales con todas las características compatibles con la publicación de Oracle.</span><span class="sxs-lookup"><span data-stu-id="c282c-109">The **Complete** option is designed to provide snapshot and transactional publications with the complete set of supported features for Oracle publishing.</span></span> <span data-ttu-id="c282c-110">La opción **Puerta de enlace** proporciona optimizaciones de diseño específicas para mejorar el rendimiento en casos en los que la replicación sirva como puerta de enlace entre sistemas.</span><span class="sxs-lookup"><span data-stu-id="c282c-110">The **Gateway** option provides specific design optimizations to improve performance for cases where replication serves as a gateway between systems.</span></span> <span data-ttu-id="c282c-111">La opción **Puerta de enlace** no se puede utilizar si tiene previsto publicar la misma tabla en varias publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="c282c-111">The **Gateway** option cannot be used if you plan to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="c282c-112">Una tabla puede aparecer como máximo en una publicación transaccional y en cualquier número de publicaciones de instantáneas si selecciona **Puerta de enlace**.</span><span class="sxs-lookup"><span data-stu-id="c282c-112">A table can appear in at most one transactional publication and any number of snapshot publications if you select **Gateway**.</span></span>  
  
 <span data-ttu-id="c282c-113">**Tiempos de espera**</span><span class="sxs-lookup"><span data-stu-id="c282c-113">**Timeouts**</span></span>  
 <span data-ttu-id="c282c-114">Especifique el tiempo durante el que el distribuidor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe intentar conectarse con el publicador de Oracle antes de que se produzca un error de tiempo de expiración.</span><span class="sxs-lookup"><span data-stu-id="c282c-114">Specify how long the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor should attempt to connect to the Oracle Publisher before a timeout error occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c282c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c282c-115">See Also</span></span>  
 <span data-ttu-id="c282c-116">[Glosario de términos de publicaciones de Oracle](non-sql/glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="c282c-116">[Glossary of Terms for Oracle Publishing](non-sql/glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="c282c-117">Optimizar el rendimiento de publicadores de Oracle</span><span class="sxs-lookup"><span data-stu-id="c282c-117">Performance Tuning for Oracle Publishers</span></span>](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
