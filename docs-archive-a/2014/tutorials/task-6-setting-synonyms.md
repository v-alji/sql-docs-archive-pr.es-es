---
title: 'Tarea 6: establecer sinónimos | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b7d35ee9-d1c9-41d9-bbc5-0ca7db93e54d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bde0c0ec7f230ba2325aa01328b191fd8fd67fa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662413"
---
# <a name="task-6-setting-synonyms"></a><span data-ttu-id="7f96b-102">Tarea 6: Definición de sinónimos</span><span class="sxs-lookup"><span data-stu-id="7f96b-102">Task 6: Setting Synonyms</span></span>
  <span data-ttu-id="7f96b-103">En esta tarea, establecerá dos valores de dominio, **USA** y **Estados Unidos**, del dominio **País** como sinónimos, siendo **Estados Unidos** el valor inicial.</span><span class="sxs-lookup"><span data-stu-id="7f96b-103">In this task, you set two domain values, **USA** and **United States**, of the **Country** domain as synonyms with **United States** as the leading value.</span></span> <span data-ttu-id="7f96b-104">Como se seleccionó la opción **Usar valores iniciales** al crear el dominio **País** , todos los valores **USA** del dominio **País** se mostrarán como **Estados Unidos** (ya que Estados Unidos es el valor inicial).</span><span class="sxs-lookup"><span data-stu-id="7f96b-104">Since the **Use Leading Values** option was selected when creating the **Country** domain, any **USA** values for the **Country** domain will be output as **United States** (as United States is the leading value).</span></span> <span data-ttu-id="7f96b-105">Vea el tema [Cambiar valores de dominio](https://msdn.microsoft.com/library/hh510408.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="7f96b-105">See [Change Domain Values](https://msdn.microsoft.com/library/hh510408.aspx) for more details.</span></span>

1.  <span data-ttu-id="7f96b-106">Seleccione **País** en la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="7f96b-106">Select **Country** from the list of domains.</span></span>

2.  <span data-ttu-id="7f96b-107">Cambie a la pestaña **Valores del dominio** .</span><span class="sxs-lookup"><span data-stu-id="7f96b-107">Switch to the **Domain Values** tab.</span></span>

3.  <span data-ttu-id="7f96b-108">Haga clic en el botón **Agregar un nuevo valor de dominio** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="7f96b-108">Click **Add new domain value** button on the toolbar.</span></span>

4.  <span data-ttu-id="7f96b-109">Escriba **USA** como valor y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="7f96b-109">Type **USA** for the value and press **ENTER**.</span></span>

5.  <span data-ttu-id="7f96b-110">Realice una selección múltiple de **Estados Unidos** y **USA** mediante las teclas CTRL o MAYÚS, haga clic con el botón secundario en los elementos seleccionados y, a continuación, haga clic en **Establecer como sinónimos**.</span><span class="sxs-lookup"><span data-stu-id="7f96b-110">Multiselect **United States** and **USA** using CTRL or SHIFT keys, right-click the selected items, and then click **Set as Synonyms**.</span></span> <span data-ttu-id="7f96b-111">DQS agrupa estos valores y designa uno de ellos como el valor inicial por el que se reemplazan los demás valores.</span><span class="sxs-lookup"><span data-stu-id="7f96b-111">DQS groups these values and designate one of the values as the leading value that the other values are replaced with.</span></span>

     <span data-ttu-id="7f96b-112">![Menú Establecer como sinónimos](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Menú Establecer como sinónimos")</span><span class="sxs-lookup"><span data-stu-id="7f96b-112">![Set as Synonyms Menu](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Set as Synonyms Menu")</span></span>

6.  <span data-ttu-id="7f96b-113">Observe que **Estados Unidos** se establece como valor inicial.</span><span class="sxs-lookup"><span data-stu-id="7f96b-113">Notice that **United States** is set as the leading value.</span></span> <span data-ttu-id="7f96b-114">Si desea que USA sea el valor inicial, puede hacer clic con el botón secundario en USA y seleccionar la opción **Establecer como principal** .</span><span class="sxs-lookup"><span data-stu-id="7f96b-114">If you want USA to be the leading value, you can right-click on USA and select **Set as Leading** option.</span></span> <span data-ttu-id="7f96b-115">En este tutorial, usamos **Estados Unidos** como valor inicial.</span><span class="sxs-lookup"><span data-stu-id="7f96b-115">For this tutorial, we use **United States** as the leading value.</span></span>

     <span data-ttu-id="7f96b-116">![Estados Unidos y EE. UU. como sinónimos](../../2014/tutorials/media/et-settingsynonyms-02.jpg "Estados Unidos y EE. UU. como sinónimos")</span><span class="sxs-lookup"><span data-stu-id="7f96b-116">![United States and USA as Synonyms](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States and USA as Synonyms")</span></span>

## <a name="next-step"></a><span data-ttu-id="7f96b-117">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="7f96b-117">Next Step</span></span>
 [<span data-ttu-id="7f96b-118">Tarea 7: Creación de un dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="7f96b-118">Task 7: Creating a Composite Domain</span></span>](../../2014/tutorials/task-7-creating-a-composite-domain.md)


