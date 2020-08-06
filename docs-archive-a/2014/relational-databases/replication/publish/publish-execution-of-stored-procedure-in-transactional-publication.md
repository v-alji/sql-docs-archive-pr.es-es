---
title: Publicar la ejecución de un procedimiento almacenado en una publicación transaccional (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- stored procedures [SQL Server replication], publishing
ms.assetid: 1d3a3525-0bc5-466f-b097-5359dc74432d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44310d45a7049701a6aecfa73301b15b0021ac6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669596"
---
# <a name="publish-the-execution-of-a-stored-procedure-in-a-transactional-publication-sql-server-management-studio"></a><span data-ttu-id="1445d-102">Publicar la ejecución de un procedimiento almacenado en una publicación transaccional (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1445d-102">Publish the Execution of a Stored Procedure in a Transactional Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="1445d-103">Utilice el cuadro de diálogo **Propiedades del artículo: \<Article>** para especificar que debe publicarse la ejecución de un procedimiento almacenado (no solo su definición).</span><span class="sxs-lookup"><span data-stu-id="1445d-103">Specify that the execution of a stored procedure (rather than just its definition) should be published in the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="1445d-104">Este cuadro de diálogo está disponible en el Asistente para nueva publicación y en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="1445d-104">This dialog box is available in the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="1445d-105">Para obtener más información sobre el uso del asistente y el acceso al cuadro de diálogo, consulte [Create a Publication](create-a-publication.md) (Crear una publicación) y [Ver y modificar propiedades de publicación](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1445d-105">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
 <span data-ttu-id="1445d-106">La definición del procedimiento (la instrucción CREATE PROCEDURE) se replica en el suscriptor cuando se inicializa la suscripción; cuando el procedimiento se ejecuta en el publicador, la replicación ejecuta el procedimiento correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1445d-106">The definition of the procedure (the CREATE PROCEDURE statement) is replicated to the Subscriber when the subscription is initialized; when the procedure is executed at the Publisher, replication executes the corresponding procedure at the Subscriber.</span></span>  
  
### <a name="to-publish-the-execution-of-a-stored-procedure"></a><span data-ttu-id="1445d-107">Para publicar la ejecución de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="1445d-107">To publish the execution of a stored procedure</span></span>  
  
1.  <span data-ttu-id="1445d-108">En la página **Artículos** del Asistente para nueva publicación o en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** , seleccione un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="1445d-108">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a stored procedure.</span></span>  
  
2.  <span data-ttu-id="1445d-109">Haga clic en **Propiedades del artículo**y, a continuación, haga clic en **Establecer propiedades del procedimiento almacenado resaltado**.</span><span class="sxs-lookup"><span data-stu-id="1445d-109">Click **Article Properties**, and then click **Set Properties of Highlighted Stored Procedure**.</span></span>  
  
3.  <span data-ttu-id="1445d-110">En el cuadro de diálogo **Propiedades del artículo: \<Article>** , especifique uno de los siguientes valores para la opción **Replicación**:</span><span class="sxs-lookup"><span data-stu-id="1445d-110">In the **Article Properties - \<Article>** dialog box, specify one of the following values for the **Replicate** option:</span></span>  
  
    -   <span data-ttu-id="1445d-111">**Ejecución del procedimiento almacenado**</span><span class="sxs-lookup"><span data-stu-id="1445d-111">**Execution of the stored procedure**</span></span>  
  
    -   <span data-ttu-id="1445d-112">**Ejecución en una transacción serializada de SP**</span><span class="sxs-lookup"><span data-stu-id="1445d-112">**Execution in a serialized transaction of the SP**</span></span>  
  
         <span data-ttu-id="1445d-113">Es la opción recomendada, ya que replica la ejecución del procedimiento solo si éste se ejecuta en el contexto de una transacción serializable.</span><span class="sxs-lookup"><span data-stu-id="1445d-113">This is the recommended option, because it replicates the procedure execution only if the procedure is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="1445d-114">Si el procedimiento almacenado se ejecuta fuera de una transacción serializable, los cambios efectuados en los datos de las tablas publicadas se replican como una serie de instrucciones de lenguaje de manipulación de datos (DML).</span><span class="sxs-lookup"><span data-stu-id="1445d-114">If the stored procedure is executed outside of a serializable transaction, changes to data in published tables are replicated as a series of data manipulation language (DML) statements.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="1445d-115">Si está en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** , haga clic en **Aceptar** para guardar y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1445d-115">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1445d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1445d-116">See Also</span></span>  
 [<span data-ttu-id="1445d-117">Publicar la ejecución de procedimientos almacenados en la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="1445d-117">Publishing Stored Procedure Execution in Transactional Replication</span></span>](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md)  
  
  
