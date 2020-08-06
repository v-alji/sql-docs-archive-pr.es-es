---
title: Asociar extensiones de archivo a un editor de código
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- file extensions [SQL Server]
- associating file extensions [SQL Server]
- Query Editor [SQL Server Management Studio], associating file extensions
ms.assetid: 193630f4-93de-4950-8f36-68702531f925
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e8cfbc89892a99971e985ffd3ff10b99f89fe53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671459"
---
# <a name="associate-file-extensions-to-a-code-editor"></a><span data-ttu-id="809e1-102">Asociar extensiones de archivo a un editor de código</span><span class="sxs-lookup"><span data-stu-id="809e1-102">Associate File Extensions to a Code Editor</span></span>
  <span data-ttu-id="809e1-103">La asociación de extensiones de archivo a un editor de código específico permite abrir un archivo con el editor de código de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] apropiado al hacer doble clic en un archivo con el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="809e1-103">Associating file extensions to a specific code editor allows you to open a file with the appropriate [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] code editor when you double-click a file in Windows Explorer.</span></span> <span data-ttu-id="809e1-104">Las extensiones que usa normalmente [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], como .sql y .mdx, se asocian durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="809e1-104">The extensions commonly used by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation.</span></span> <span data-ttu-id="809e1-105">Las nuevas extensiones de archivo también deben estar asociadas a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="809e1-105">New file extensions must also be associated to [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in the file system.</span></span> <span data-ttu-id="809e1-106">Puede utilizar esta característica para abrir archivos creados con otros editores o de los cuales ha cambiado el nombre, como las copias de seguridad de archivos .sql cuya extensión se ha cambiado por .bak.</span><span class="sxs-lookup"><span data-stu-id="809e1-106">You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.</span></span>  
  
 <span data-ttu-id="809e1-107">Este proceso incluye dos pasos.</span><span class="sxs-lookup"><span data-stu-id="809e1-107">There are two steps in the process.</span></span> <span data-ttu-id="809e1-108">En primer lugar, se asocia la extensión con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y, a continuación, con un editor de código determinado.</span><span class="sxs-lookup"><span data-stu-id="809e1-108">First associate the extension with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-sql-server-management-studio"></a><span data-ttu-id="809e1-109">Para asociar una nueva extensión de archivo con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="809e1-109">To associate a new file extension with SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="809e1-110">En el menú **Inicio** , seleccione **Todos los programas**, **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.</span><span class="sxs-lookup"><span data-stu-id="809e1-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="809e1-111">En el menú **Herramientas** del Explorador de Windows, haga clic en **Opciones de carpeta**.</span><span class="sxs-lookup"><span data-stu-id="809e1-111">In Windows Explorer, on the **Tools** menu, click **Folder Options**.</span></span>  
  
3.  <span data-ttu-id="809e1-112">En la pestaña **Tipos de archivo** del cuadro de diálogo **Opciones de carpeta** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="809e1-112">In the **Folder Options** dialog box, on the **File Types** tab, click **New**.</span></span>  
  
4.  <span data-ttu-id="809e1-113">En el cuadro **Extensión de archivo** del cuadro de diálogo **Crear nueva extensión** , escriba la nueva extensión de archivo que desea asociar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="809e1-113">In the **Create New Extension** dialog box, in the **File Extension** box, type the new file extension that you want to associate, and then click **OK**.</span></span> <span data-ttu-id="809e1-114">No escriba el nombre de la extensión con un punto.</span><span class="sxs-lookup"><span data-stu-id="809e1-114">Do not start the extension with a period.</span></span>  
  
5.  <span data-ttu-id="809e1-115">En el cuadro **Tipos de archivo registrados** , haga clic en la nueva extensión y, a continuación, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="809e1-115">In the **Registered file** types box, click on your new extension, and then click **Change**.</span></span>  
  
6.  <span data-ttu-id="809e1-116">En el cuadro de diálogo **Abrir con**, haga clic en **SSMS - SQL Server Management Studio** y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="809e1-116">In the **Open With** dialog box, click **SSMS - SQL Server Management Studio**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="809e1-117">Haga clic en **Cerrar** para cerrar el cuadro de diálogo **Opciones de carpeta** y, a continuación, cierre el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="809e1-117">Click **Close** to close the **Folder Options** dialog box, and then close Windows Explorer.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-a-code-editor-in-sql-server-management-studio"></a><span data-ttu-id="809e1-118">Para asociar una nueva extensión de archivo con un editor de código en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="809e1-118">To associate a new file extension with a code editor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="809e1-119">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="809e1-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="809e1-120">En el cuadro de diálogo **Opciones** , haga clic en **Editor de texto**y, a continuación, en **Extensión de archivo**.</span><span class="sxs-lookup"><span data-stu-id="809e1-120">In the **Options** dialog box, click **Text Editor**, and then click **File Extension**.</span></span>  
  
3.  <span data-ttu-id="809e1-121">En el cuadro **Extensión** , escriba la nueva extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="809e1-121">In the **Extension** box, type your new file extension.</span></span>  
  
4.  <span data-ttu-id="809e1-122">En el cuadro **Editor** , haga clic en el editor de código que desea utilizar para abrir este tipo de archivo, haga clic en **Agregar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="809e1-122">In the **Editor** box, click the code editor that you wish to use to open this file type, click **Add**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809e1-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="809e1-123">See Also</span></span>  
 [<span data-ttu-id="809e1-124">Ssms (Utilidad)</span><span class="sxs-lookup"><span data-stu-id="809e1-124">Ssms Utility</span></span>](../../ssms/ssms-utility.md)  
  
  
