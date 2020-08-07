---
title: Administración de espacios de tabla de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3624aed38a7a5bf75e0c0807aa8d3657156264f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746920"
---
# <a name="manage-oracle-tablespaces"></a><span data-ttu-id="d558d-102">Administrar espacios de tabla de Oracle</span><span class="sxs-lookup"><span data-stu-id="d558d-102">Manage Oracle Tablespaces</span></span>
  <span data-ttu-id="d558d-103">Un espacio de tabla es una unidad de almacenamiento de base de datos que equivale aproximadamente a un grupo de archivos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d558d-103">A tablespace is a unit of database storage that is roughly equivalent to a file group in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d558d-104">Los espacios de tabla permiten el almacenamiento y la administración de objetos de base de datos en grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="d558d-104">Tablespaces allow storage and management of database objects within individual groups.</span></span> <span data-ttu-id="d558d-105">Para obtener más información, vea la documentación de Oracle.</span><span class="sxs-lookup"><span data-stu-id="d558d-105">For more information, see the Oracle documentation.</span></span>  
  
 <span data-ttu-id="d558d-106">Al configurar una tabla como parte de una publicación de Oracle, puede especificar un espacio de tabla de Oracle existente, para utilizarlo al almacenar la información de registro de la replicación.</span><span class="sxs-lookup"><span data-stu-id="d558d-106">When you configure a table as part of an Oracle publication, you can optionally specify an existing Oracle tablespace to be used when storing replication logging information.</span></span> <span data-ttu-id="d558d-107">Si no lo especifica, el espacio de tabla que se utilizará para los objetos de la replicación será el espacio de tabla predeterminado asociado con el esquema de usuario administrativo de la replicación configurado al configurar el publicador.</span><span class="sxs-lookup"><span data-stu-id="d558d-107">If unspecified, the tablespace for the replication objects is the default tablespace associated with the replication administrative user schema that was configured when configuring the Publisher.</span></span>  
  
 <span data-ttu-id="d558d-108">**Para especificar un espacio de tabla para una tabla de registro de artículos**:</span><span class="sxs-lookup"><span data-stu-id="d558d-108">**To specify a tablespace for an article logging table**:</span></span>  
  
-   <span data-ttu-id="d558d-109">Especifique un espacio de tabla en el cuadro de diálogo **Propiedades del artículo** .</span><span class="sxs-lookup"><span data-stu-id="d558d-109">Specify a tablespace in the **Article Properties** dialog box.</span></span> <span data-ttu-id="d558d-110">Para obtener más información sobre el acceso a este cuadro de diálogo, vea [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d558d-110">For more information about accessing this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="d558d-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d558d-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span></span> <span data-ttu-id="d558d-112">Para utilizar **sp_changearticle**, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d558d-112">To use **sp_changearticle**, specify the following:</span></span>  
  
    -   <span data-ttu-id="d558d-113">Nombre del publicador de Oracle para el parámetro **@publisher** .</span><span class="sxs-lookup"><span data-stu-id="d558d-113">The name of the Oracle Publisher for the parameter **@publisher**.</span></span>  
  
    -   <span data-ttu-id="d558d-114">El nombre de la publicación de Oracle para el parámetro **@publication** .</span><span class="sxs-lookup"><span data-stu-id="d558d-114">The name of the Oracle publication for the parameter **@publication**.</span></span>  
  
    -   <span data-ttu-id="d558d-115">Nombre del artículo para el parámetro **@article** .</span><span class="sxs-lookup"><span data-stu-id="d558d-115">The name of the article for the parameter **@article**.</span></span>  
  
    -   <span data-ttu-id="d558d-116">Un valor de ' Tablespaces ' para el parámetro **@property** .</span><span class="sxs-lookup"><span data-stu-id="d558d-116">A value of 'tablespace' for the parameter **@property**.</span></span>  
  
    -   <span data-ttu-id="d558d-117">Nombre del espacio de tablas para el parámetro **@value** .</span><span class="sxs-lookup"><span data-stu-id="d558d-117">The name of the tablespace for the parameter **@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d558d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d558d-118">See Also</span></span>  
 <span data-ttu-id="d558d-119">[Configurar un publicador de Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="d558d-119">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="d558d-120">Objetos creados en el publicador de Oracle</span><span class="sxs-lookup"><span data-stu-id="d558d-120">Objects Created on the Oracle Publisher</span></span>](objects-created-on-the-oracle-publisher.md)  
  
  
