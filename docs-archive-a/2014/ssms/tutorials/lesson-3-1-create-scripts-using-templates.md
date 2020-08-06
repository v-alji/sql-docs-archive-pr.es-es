---
title: Crear scripts mediante plantillas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ed48014c-3fc9-48ff-8c0f-8d1822195f14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b404ecc505e93c302e4c737f9c0b0161d9015519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746662"
---
# <a name="create-scripts-using-templates"></a><span data-ttu-id="03c04-102">Crear scripts mediante plantillas</span><span class="sxs-lookup"><span data-stu-id="03c04-102">Create Scripts Using Templates</span></span>
  <span data-ttu-id="03c04-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ofrece un gran número de plantillas de script que incluyen instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] para muchas de las tareas habituales.</span><span class="sxs-lookup"><span data-stu-id="03c04-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides a large number of script templates containing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for many common tasks.</span></span> <span data-ttu-id="03c04-104">Estas plantillas contienen parámetros para los valores proporcionados por el usuario como, por ejemplo, un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="03c04-104">These templates contain parameters for the user-provided values such as a table name.</span></span> <span data-ttu-id="03c04-105">Mediante los parámetros, puede escribir el nombre una sola vez y copiarlo automáticamente en todas las ubicaciones necesarias del script.</span><span class="sxs-lookup"><span data-stu-id="03c04-105">Using the parameters, you can type the name once and then automatically copy the name to all the necessary locations within the script.</span></span> <span data-ttu-id="03c04-106">Puede crear sus propias plantillas personalizadas para los scripts que escriba con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="03c04-106">You can write your own custom templates to support the scripts that you write most often.</span></span> <span data-ttu-id="03c04-107">También puede reorganizar el árbol de plantillas, mover las plantillas o crear carpetas nuevas para alojarlas.</span><span class="sxs-lookup"><span data-stu-id="03c04-107">You can also reorganize the template tree, moving templates or creating new folders to hold the templates.</span></span> <span data-ttu-id="03c04-108">En la práctica siguiente, utilizará una plantilla para crear una base de datos, especificando una plantilla de intercalación.</span><span class="sxs-lookup"><span data-stu-id="03c04-108">In the following practice, you will use a template to create a database, specifying collation template.</span></span>  
  
## <a name="using-templates"></a><span data-ttu-id="03c04-109">Usar plantillas</span><span class="sxs-lookup"><span data-stu-id="03c04-109">Using Templates</span></span>  
  
#### <a name="to-create-a-script-using-a-template"></a><span data-ttu-id="03c04-110">Para crear un script mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="03c04-110">To create a script using a template</span></span>  
  
1.  <span data-ttu-id="03c04-111">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], en el menú **Ver** , haga clic en el **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="03c04-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="03c04-112">Las plantillas del Explorador de plantillas están organizadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="03c04-112">The templates in Template Explorer are organized into groups.</span></span> <span data-ttu-id="03c04-113">Expanda **Base de datos**y, después, haga doble clic en **Crear base de datos**.</span><span class="sxs-lookup"><span data-stu-id="03c04-113">Expand **Database**, and then double-click **Create Database**.</span></span>  
  
3.  <span data-ttu-id="03c04-114">En el cuadro de diálogo **Conectarse al motor de base de datos** , rellene la información de conexión y luego haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="03c04-114">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="03c04-115">Se abrirá una ventana nueva del Editor de consultas, que incluye el contenido de la plantilla **Crear base de datos** .</span><span class="sxs-lookup"><span data-stu-id="03c04-115">A new Query Editor window opens, containing the contents of the **Create Database** template.</span></span>  
  
4.  <span data-ttu-id="03c04-116">En el menú **Consulta** , haga clic en **Especificar valores para parámetros de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="03c04-116">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="03c04-117">En el cuadro de diálogo **Especificar valores para parámetros de plantilla** , la columna **Valor** contiene un valor recomendado para el parámetro **Nombre de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="03c04-117">In the **Specify Values for Template Parameters** dialog box, the **Value** column contains a suggested value for the **Database_Name** parameter.</span></span> <span data-ttu-id="03c04-118">En el cuadro de parámetro **Nombre de la base de datos** , escriba **Marketing**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="03c04-118">In the **Database Name** parameter box, type **Marketing**, and then click **OK**.</span></span> <span data-ttu-id="03c04-119">Observe que "Marketing" aparece en varias ubicaciones del script.</span><span class="sxs-lookup"><span data-stu-id="03c04-119">Note how "Marketing" is inserted into the script in several locations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="03c04-120">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="03c04-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="03c04-121">Crear plantillas personalizadas</span><span class="sxs-lookup"><span data-stu-id="03c04-121">Create Custom Templates</span></span>](lesson-3-2-create-custom-templates.md)  
  
  
