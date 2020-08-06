---
title: Administrar archivos con codificación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- files [SQL Server Management Studio]
- encoding [SQL Server Management Studio]
- files [SQL Server Management Studio], encoding
ms.assetid: 919544c9-59f0-4cc6-bb2a-f1ad671eb74b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9b0aaa123001fed3f6ad42ea9d642e4007e2640f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677989"
---
# <a name="manage-files-with-encoding"></a><span data-ttu-id="a7b5b-102">Administrar archivos con codificación</span><span class="sxs-lookup"><span data-stu-id="a7b5b-102">Manage Files with Encoding</span></span>
  <span data-ttu-id="a7b5b-103">Para facilitar la visualización del código en un idioma concreto y en una plataforma específica, puede asociar una codificación de caracteres determinada a un archivo.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-103">To facilitate the display of your code in a particular language and on a particular platform, you can associate a particular character encoding with a file.</span></span>  
  
## <a name="opening-files"></a><span data-ttu-id="a7b5b-104">Abrir archivos</span><span class="sxs-lookup"><span data-stu-id="a7b5b-104">Opening Files</span></span>  
 <span data-ttu-id="a7b5b-105">Puede elegir el editor que desea utilizar para modificar el archivo.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-105">You can choose the editor you want to use to edit the file.</span></span>  
  
#### <a name="to-open-a-file-with-a-specific-editor"></a><span data-ttu-id="a7b5b-106">Para abrir un archivo con un editor específico</span><span class="sxs-lookup"><span data-stu-id="a7b5b-106">To open a file with a specific editor</span></span>  
  
1.  <span data-ttu-id="a7b5b-107">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-107">On the **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="a7b5b-108">En el cuadro de diálogo **Abrir archivo** , seleccione el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-108">In the **Open File** dialog box, select the file name.</span></span>  
  
3.  <span data-ttu-id="a7b5b-109">Haga clic en la flecha situada junto al botón **Abrir** y haga clic en**Abrir con** en el menú que aparece.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-109">Click the arrow next to the **Open** button, and then click**Open With** from the menu that appears.</span></span>  
  
4.  <span data-ttu-id="a7b5b-110">En la lista **Seleccione el programa que desee usar** , seleccione un editor y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-110">In the **Select a program to open** list, select an editor, and then click **Open**.</span></span> <span data-ttu-id="a7b5b-111">Para abrir el archivo con una codificación determinada, seleccione un editor compatible con la codificación, como el Editor de consultas de SQL con codificación o el Editor XML con codificación.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-111">To open the file with a particular encoding, select an editor with encoding support, such as SQL Query Editor with Encoding or XML Editor with Encoding.</span></span>  
  
## <a name="saving-files"></a><span data-ttu-id="a7b5b-112">Guardar archivos</span><span class="sxs-lookup"><span data-stu-id="a7b5b-112">Saving Files</span></span>  
 <span data-ttu-id="a7b5b-113">También se puede guardar el código con una codificación Unicode o una página de códigos distinta para que sea compatible con varios idiomas, como Europao occidental o Europao oriental.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-113">You can also save your code with a Unicode encoding or a different code page to support various languages, such as Western European or Eastern European.</span></span> <span data-ttu-id="a7b5b-114">Puede asociar una codificación de caracteres concreta a un archivo para facilitar la visualización del código en ese idioma, así como un tipo de fin de línea para ser compatible con un sistema operativo determinado.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-114">You can associate a particular character encoding with a file to facilitate the display of your code in that language, as well as a line-ending type to support a particular operating system.</span></span> <span data-ttu-id="a7b5b-115">Además, algunos caracteres, cuando se utilizan en los nombres de archivo, no se pueden guardar a menos que se haga con codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-115">Also, some characters, when used in file names, cannot be saved unless they are saved with Unicode encoding.</span></span>  
  
#### <a name="to-save-a-file-with-a-different-encoding-or-line-ending-type"></a><span data-ttu-id="a7b5b-116">Para guardar un archivo con una codificación o un tipo de fin de línea diferente</span><span class="sxs-lookup"><span data-stu-id="a7b5b-116">To save a file with a different encoding or line ending type</span></span>  
  
1.  <span data-ttu-id="a7b5b-117">En el menú **Archivo** , haga clic en **Guardar \<filename> como**.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-117">On the **File** menu, click **Save \<filename> As**.</span></span>  
  
2.  <span data-ttu-id="a7b5b-118">En el cuadro de diálogo **Guardar archivo como** , expanda el botón **Guardar** y, luego, haga clic en **Guardar con codificación**.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-118">In the **Save File As** dialog, expand the **Save** button, and then click **Save with Encoding**.</span></span>  
  
3.  <span data-ttu-id="a7b5b-119">En el cuadro de diálogo **Opciones avanzadas para guardar** , seleccione la codificación que desea en la lista **Codificación** .</span><span class="sxs-lookup"><span data-stu-id="a7b5b-119">In the **Advanced Save Options** dialog box, select the encoding you want from the **Encoding** list.</span></span>  
  
4.  <span data-ttu-id="a7b5b-120">En la lista **Fin de línea**, seleccione el tipo de fin de línea que desea.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-120">From the **Line Endings**list, select the type of line ending you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7b5b-121">Si guarda el archivo con codificación Unicode, éste deberá protegerse en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe como un archivo binario, puesto que este programa no es compatible con la combinación, la comparación ni la comprobación de diferencias entre archivos guardados como Unicode.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-121">If you save your file your file with Unicode encoding, the file should be checked into [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe as a binary file because Visual SourceSafe does not support merging, comparing, and showing differences between files that are saved as Unicode.</span></span>  
  
 <span data-ttu-id="a7b5b-122">Si utiliza Visual SourceSafe para almacenar archivos con ANSI, UTF8 o Unicode, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="a7b5b-122">If you are using Visual SourceSafe to store files with ANSI, UTF8, or Unicode, be aware of the following limitations for each:</span></span>  
  
-   <span data-ttu-id="a7b5b-123">Los archivos ANSI solo permiten caracteres compatibles con la página de códigos actual, lo que limita el uso internacional.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-123">ANSI files allow only characters that are supported in the current code page, which limits international use.</span></span>  
  
-   <span data-ttu-id="a7b5b-124">Los archivos Unicode utilizan la desprotección compartida, la comprobación de diferencias o la funcionalidad de combinación porque se administran como archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-124">Unicode files cannot use shared checkout, difference checking, or merging functionality because they are handled as binary files.</span></span> <span data-ttu-id="a7b5b-125">Este formato se puede utilizar en archivos internacionales.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-125">You can use this format in international files.</span></span>  
  
-   <span data-ttu-id="a7b5b-126">Los archivos UTF8 no funcionan de forma segura con Visual SourceSafe porque los cambios que ocasionan problemas para los editores de archivos UTF8 se realizan durante la protección, la desprotección, la comprobación de diferencias y la combinación.</span><span class="sxs-lookup"><span data-stu-id="a7b5b-126">UTF8 files do not work safely with Visual SourceSafe because changes that cause problems for UTF8 file editors are made during check in, check out, difference checking, and merging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b5b-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7b5b-127">See Also</span></span>  
 <span data-ttu-id="a7b5b-128">[Archivos que administran soluciones y proyectos](files-that-manage-solutions-and-projects.md) </span><span class="sxs-lookup"><span data-stu-id="a7b5b-128">[Files That Manage Solutions and Projects](files-that-manage-solutions-and-projects.md) </span></span>  
 [<span data-ttu-id="a7b5b-129">Asociar extensiones de archivo a un editor de código</span><span class="sxs-lookup"><span data-stu-id="a7b5b-129">Associate File Extensions to a Code Editor</span></span>](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md)  
  
  
