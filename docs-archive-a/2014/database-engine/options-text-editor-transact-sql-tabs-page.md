---
title: 'Opciones (editor de texto-Transact-SQL: Página tabulaciones) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Tabs
dev_langs:
- TSQL
ms.assetid: a4499784-67f7-46ef-9f7c-2d0fdd117a52
author: rothja
ms.author: jroth
ms.openlocfilehash: 6caa659d13f8089fdd9f990a55e503657ef72a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674985"
---
# <a name="options-text-editor---transact-sql---tabs-page"></a><span data-ttu-id="c5059-102">Opciones (editor de texto-Transact-SQL-página tabulaciones)</span><span class="sxs-lookup"><span data-stu-id="c5059-102">Options (Text Editor - Transact-SQL - Tabs Page)</span></span>
  <span data-ttu-id="c5059-103">Utilice este cuadro de diálogo para cambiar el comportamiento de tabulación del Editor de consultas de [!INCLUDE[ssDE](../includes/ssde-md.md)] , que se utiliza para programar scripts de [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5059-103">Use this dialog to change the tabbing behavior of the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor, which is used to program [!INCLUDE[tsql](../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="c5059-104">Para mostrar estas opciones de configuración, haga clic en **Opciones** en el menú **Herramientas** , expanda la carpeta **Transact-SQL** , expanda la subcarpeta **SQL** y, a continuación, haga clic en **Tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="c5059-104">To display these settings, click **Options** on the **Tools** menu, expand the **Text Editor** folder, expand the **Transact-SQL** subfolder and then click **Tabs**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="c5059-105">Establecer opciones en varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="c5059-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="c5059-106">Las opciones del Editor de consultas de [!INCLUDE[ssDE](../includes/ssde-md.md)] también se pueden establecer en el cuadro de diálogo **Tabulaciones de Todos los lenguajes**.</span><span class="sxs-lookup"><span data-stu-id="c5059-106">Options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor can also be set in the **All Languages Tabs** dialog.</span></span> <span data-ttu-id="c5059-107">Si utiliza los cuadros de diálogo **Todos los lenguajes** para establecer diferentes opciones para los demás editores de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , como los editores MDX o DMX, debe restablecer las opciones del Editor de consultas del [!INCLUDE[ssDE](../includes/ssde-md.md)] mediante este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5059-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor options using this dialog.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="c5059-108">Sangrías</span><span class="sxs-lookup"><span data-stu-id="c5059-108">Indenting</span></span>  
 <span data-ttu-id="c5059-109">**None**</span><span class="sxs-lookup"><span data-stu-id="c5059-109">**None**</span></span>  
 <span data-ttu-id="c5059-110">Cuando se selecciona esta opción, no se aplica ninguna sangría a la nueva línea que se crea al presionar ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c5059-110">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="c5059-111">El cursor se coloca en la primera columna de la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="c5059-111">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="c5059-112">**Bloquear**</span><span class="sxs-lookup"><span data-stu-id="c5059-112">**Block**</span></span>  
 <span data-ttu-id="c5059-113">Cuando se selecciona esta opción, se aplica una sangría de forma automática a la nueva línea que se crea al presionar ENTRAR, a la misma distancia que la línea anterior.</span><span class="sxs-lookup"><span data-stu-id="c5059-113">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line.</span></span>  
  
 <span data-ttu-id="c5059-114">**Automática**</span><span class="sxs-lookup"><span data-stu-id="c5059-114">**Smart**</span></span>  
 <span data-ttu-id="c5059-115">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c5059-115">This option is unavailable.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="c5059-116">Pestañas</span><span class="sxs-lookup"><span data-stu-id="c5059-116">Tabs</span></span>  
 <span data-ttu-id="c5059-117">**Tamaño de tabulación**</span><span class="sxs-lookup"><span data-stu-id="c5059-117">**Tab size**</span></span>  
 <span data-ttu-id="c5059-118">Establece la distancia en espacios entre las tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="c5059-118">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="c5059-119">El valor predeterminado es cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="c5059-119">The default is four spaces.</span></span>  
  
 <span data-ttu-id="c5059-120">**Tamaño de sangría**</span><span class="sxs-lookup"><span data-stu-id="c5059-120">**Indent size**</span></span>  
 <span data-ttu-id="c5059-121">Establece el tamaño en espacios de una sangría automática.</span><span class="sxs-lookup"><span data-stu-id="c5059-121">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="c5059-122">El valor predeterminado es cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="c5059-122">The default is four spaces.</span></span> <span data-ttu-id="c5059-123">Se insertan caracteres de tabulación, de espacio o ambos para rellenar el tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="c5059-123">Tab characters, space characters, or both are inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="c5059-124">**Insertar espacios**</span><span class="sxs-lookup"><span data-stu-id="c5059-124">**Insert spaces**</span></span>  
 <span data-ttu-id="c5059-125">Cuando se selecciona esta opción, las operaciones de aplicación de sangrías solo insertan caracteres de espacio, pero no caracteres de tabulación.</span><span class="sxs-lookup"><span data-stu-id="c5059-125">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="c5059-126">Si **tamaño de sangría** se establece en 5, por ejemplo, se insertarán cinco caracteres de espacio cada vez que se presione la tecla TAB o se haga clic en el botón **aumentar sangría** en la barra de herramientas de la [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ventana principal.</span><span class="sxs-lookup"><span data-stu-id="c5059-126">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar in the main [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] window.</span></span>  
  
 <span data-ttu-id="c5059-127">**Mantener tabulaciones**</span><span class="sxs-lookup"><span data-stu-id="c5059-127">**Keep tabs**</span></span>  
 <span data-ttu-id="c5059-128">Cuando se selecciona esta opción, las operaciones de aplicación de sangrías insertan todos los caracteres de tabulación posibles.</span><span class="sxs-lookup"><span data-stu-id="c5059-128">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="c5059-129">Cada carácter de tabulación rellena el número de espacios especificados en **Tamaño de tabulación**.</span><span class="sxs-lookup"><span data-stu-id="c5059-129">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="c5059-130">Si **Tamaño de sangría** no es un múltiplo par de **Tamaño de tabulación**, se agregarán caracteres de espacio para rellenar la diferencia.</span><span class="sxs-lookup"><span data-stu-id="c5059-130">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
