---
title: Opciones (editor de texto-XML-Página varios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 1a9509f0-c663-4b31-b396-7f5dc4371651
author: rothja
ms.author: jroth
ms.openlocfilehash: d937368d30122442ccbc40372a6b8e1cabc141e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743622"
---
# <a name="options-text-editor---xml---miscellaneous-page"></a><span data-ttu-id="ce0f9-102">Opciones (Editor de texto - XML - Página Varios)</span><span class="sxs-lookup"><span data-stu-id="ce0f9-102">Options (Text Editor - XML - Miscellaneous Page)</span></span>

<span data-ttu-id="ce0f9-103">El cuadro de diálogo **Opciones** permite modificar las opciones de finalización automática y esquema del Editor XML.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-103">The **Options** dialog box lets you change the autocompletion and schema settings for the XML Editor.</span></span> <span data-ttu-id="ce0f9-104">Estas opciones se encuentran disponibles cuando, en el menú **Herramientas** , se hace clic en **Opciones**, se expande la carpeta **Editor de texto** , se hace clic en **XML** y después se selecciona **Varios** .</span><span class="sxs-lookup"><span data-stu-id="ce0f9-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, click **XML** and then click **Miscellaneous** .</span></span>  
  
## <a name="auto-insert"></a><span data-ttu-id="ce0f9-105">Inserción automática</span><span class="sxs-lookup"><span data-stu-id="ce0f9-105">Auto Insert</span></span>  
 <span data-ttu-id="ce0f9-106">**Etiquetas de cierre**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-106">**Close tags**</span></span>  
 <span data-ttu-id="ce0f9-107">El Editor de texto agrega etiquetas de cierre al crear elementos XML.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-107">The Text Editor adds close tags when authoring XML elements.</span></span> <span data-ttu-id="ce0f9-108">Si se selecciona la etiqueta de inicio de un elemento, el editor inserta la etiqueta de cierre correspondiente, incluido el prefijo de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-108">If an element start tag is selected, the editor inserts the matching close tag, including a matching namespace prefix.</span></span> <span data-ttu-id="ce0f9-109">Esta casilla está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-109">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="ce0f9-110">**Comillas de atributo**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-110">**Attribute quotes**</span></span>  
 <span data-ttu-id="ce0f9-111">Al crear atributos XML, el editor inserta los caracteres `="``"` y coloca el símbolo de intercalación (**^)** dentro de las comillas.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-111">When authoring XML attributes, the editor inserts the `="``"` characters and positions the caret (**^)** inside the quotation marks.</span></span> <span data-ttu-id="ce0f9-112">Esta casilla está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-112">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="ce0f9-113">**Declaraciones de espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-113">**Namespace declarations**</span></span>  
 <span data-ttu-id="ce0f9-114">El editor inserta automáticamente declaraciones de espacios de nombres cuando son necesarias.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-114">The editor automatically inserts namespace declarations wherever they are needed.</span></span> <span data-ttu-id="ce0f9-115">Esta casilla está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-115">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="ce0f9-116">**Otro tipo de marcado (Comentarios, CDATA)**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-116">**Other markup (Comments, CDATA)**</span></span>  
 <span data-ttu-id="ce0f9-117">Finalización automática de comentarios, CDATA, DOCTYPE, instrucciones de proceso y otro tipo de marcado.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-117">Comments, CDATA, DOCTYPE, processing instructions, and other markup is autocompleted.</span></span> <span data-ttu-id="ce0f9-118">Esta casilla está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-118">This check box is selected by default.</span></span>  
  
## <a name="network"></a><span data-ttu-id="ce0f9-119">Red</span><span class="sxs-lookup"><span data-stu-id="ce0f9-119">Network</span></span>  
 <span data-ttu-id="ce0f9-120">**Descargar automáticamente DTD y esquemas**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-120">**Automatically download DTDs and schemas**</span></span>  
 <span data-ttu-id="ce0f9-121">Los esquemas y las definiciones de tipos de documentos (DTD) se descargan automáticamente desde ubicaciones HTTP.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-121">Schemas and document type definitions (DTDs) are automatically downloaded from HTTP locations.</span></span> <span data-ttu-id="ce0f9-122">Esta función utiliza System.Net con la opción de detección de servidores proxy automáticos habilitada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-122">This feature uses System.Net with autoproxy server detection enabled.</span></span> <span data-ttu-id="ce0f9-123">Esta casilla está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-123">This check box is selected by default.</span></span>  
  
## <a name="outlining"></a><span data-ttu-id="ce0f9-124">esquematizar</span><span class="sxs-lookup"><span data-stu-id="ce0f9-124">Outlining</span></span>  
 <span data-ttu-id="ce0f9-125">**Especificar el modo de esquematización al abrir los archivos**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-125">**Enter outlining mode when files open**</span></span>  
 <span data-ttu-id="ce0f9-126">Activa la función de esquematización al abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-126">Turns on the outlining feature when a file is opened.</span></span> <span data-ttu-id="ce0f9-127">Esta casilla está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-127">This check box is selected by default.</span></span>  
  
## <a name="caching"></a><span data-ttu-id="ce0f9-128">Almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="ce0f9-128">Caching</span></span>  
 <span data-ttu-id="ce0f9-129">**Esquemas**</span><span class="sxs-lookup"><span data-stu-id="ce0f9-129">**Schemas**</span></span>  
 <span data-ttu-id="ce0f9-130">Especifica la ubicación de la caché de esquemas.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-130">Specifies the location of the schema cache.</span></span> <span data-ttu-id="ce0f9-131">El botón Examinar (...) abre la ubicación de la caché de esquemas actual en una ventana nueva.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-131">The Browse button (...) opens the current schema cache location in a new window.</span></span> <span data-ttu-id="ce0f9-132">La ubicación predeterminada es *\<Management Studio install directory>* \Xml\Schemas.</span><span class="sxs-lookup"><span data-stu-id="ce0f9-132">The default location is *\<Management Studio install directory>* \Xml\Schemas.</span></span>  
