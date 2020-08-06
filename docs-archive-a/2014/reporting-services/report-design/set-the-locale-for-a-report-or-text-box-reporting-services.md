---
title: Establecer la configuración regional de un informe o un cuadro de texto (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- locales [Reporting Services]
ms.assetid: df115b01-184b-47f0-b5ec-0ad965ff9bee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb2b0cbd6e4216138520834216358ee455729386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663903"
---
# <a name="set-the-locale-for-a-report-or-text-box-reporting-services"></a><span data-ttu-id="d8213-102">Establecer la configuración regional de un informe o un cuadro de texto (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="d8213-102">Set the Locale for a Report or Text Box (Reporting Services)</span></span>
  <span data-ttu-id="d8213-103">La propiedad **Language** de un informe o un cuadro de texto contiene la configuración regional, que determina los formatos predeterminados para mostrar los datos de informe que difieren según el idioma y la región, como por ejemplo, la fecha, la moneda o los valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="d8213-103">The **Language** property on a report or a text box contains the locale setting, which determines the default formats for displaying report data that differ by language and region, for example, date, currency, or number values.</span></span> <span data-ttu-id="d8213-104">La propiedad **Language** de un cuadro de texto invalida la propiedad **Language** del informe.</span><span class="sxs-lookup"><span data-stu-id="d8213-104">The **Language** property on a text box overrides the **Language** property on the report.</span></span> <span data-ttu-id="d8213-105">Si no se especifica ningún valor para **Language**, Reporting Services usa la configuración regional del sistema operativo del servidor de informes para los informes publicados o la del equipo en que se crea el informe para la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="d8213-105">If no value is specified for **Language**, Reporting Services uses the locale of the operating system on the report server for published reports or of the report authoring computer for report preview.</span></span>  
  
 <span data-ttu-id="d8213-106">Para los informes HTML, puede invalidar el valor de **Language** predeterminado y usar el idioma especificado por el encabezado HTTP del cliente de explorador usando el campo integrado User!Language en una expresión para la propiedad **Language** de un informe o un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d8213-106">For HTML reports, you can override the default **Language** value and use the language specified by the HTTP header of the browser client by using the built-in field User!Language in an expression for the **Language** property of a report or a text box.</span></span>  
  
 <span data-ttu-id="d8213-107">También puede especificar la propiedad **Language** para un informe en una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="d8213-107">You can also specify the **Language** property for a report in a URL.</span></span> <span data-ttu-id="d8213-108">Para más información, vea [Establecer el idioma para los parámetros de informe en una dirección URL](../set-the-language-for-report-parameters-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="d8213-108">For more information, see [Set the Language for Report Parameters in a URL](../set-the-language-for-report-parameters-in-a-url.md).</span></span>  
  
### <a name="to-set-the-locale-for-a-report"></a><span data-ttu-id="d8213-109">Para establecer la configuración regional de un informe</span><span class="sxs-lookup"><span data-stu-id="d8213-109">To set the locale for a report</span></span>  
  
1.  <span data-ttu-id="d8213-110">En la vista Diseño, haga clic fuera de la superficie de diseño del informe para seleccionar el informe.</span><span class="sxs-lookup"><span data-stu-id="d8213-110">In Design view, click outside the report design surface to select the report.</span></span>  
  
2.  <span data-ttu-id="d8213-111">En el panel Propiedades, en la propiedad **Language** , escriba o seleccione el idioma que desea usar para el informe.</span><span class="sxs-lookup"><span data-stu-id="d8213-111">In the Properties pane, for the **Language** property, type or select the language that you want to use for the report.</span></span>  
  
### <a name="to-set-the-locale-for-a-text-box"></a><span data-ttu-id="d8213-112">Para establecer la configuración regional de un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="d8213-112">To set the locale for a text box</span></span>  
  
1.  <span data-ttu-id="d8213-113">En la vista Diseño, seleccione el cuadro de texto al que desea aplicar la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="d8213-113">In Design view, select the text box to which you want to apply the locale settings.</span></span>  
  
2.  <span data-ttu-id="d8213-114">En el panel Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8213-114">In the Properties pane, do the following:</span></span>  
  
    -   <span data-ttu-id="d8213-115">En la propiedad **Calendar** , escriba o seleccione el calendario que desea usar para las fechas.</span><span class="sxs-lookup"><span data-stu-id="d8213-115">For the **Calendar** property, type or select the calendar that you want to use for dates.</span></span>  
  
    -   <span data-ttu-id="d8213-116">En la propiedad **Direction** , escriba o seleccione la dirección en que se escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="d8213-116">For the **Direction** property, type or select the direction in which the text is written.</span></span>  
  
    -   <span data-ttu-id="d8213-117">En la propiedad **Language** , escriba o seleccione el idioma que desea usar para el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d8213-117">For the **Language** property, type or select the language that you want to use for the text box.</span></span> <span data-ttu-id="d8213-118">Este valor invalida la propiedad **Language** para el informe.</span><span class="sxs-lookup"><span data-stu-id="d8213-118">This value overrides the **Language** property for the Report.</span></span>  
  
    -   <span data-ttu-id="d8213-119">En la propiedad **NumeralLanguage** , escriba o seleccione el formato que desea utilizar para los números del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d8213-119">For the **NumeralLanguage** property, type or select the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="d8213-120">En la propiedad **NumeralVariant** , escriba o seleccione la variante de formato que desea usar para los números del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d8213-120">For the **NumeralVariant** property, type or select the variant of the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="d8213-121">En la propiedad **UnicodeBiDi** , seleccione el nivel de incrustación bidireccional que se va a usar en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d8213-121">For the **UnicodeBiDi** property, select the level of bidirectional embedding to use in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8213-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8213-122">See Also</span></span>  
 [<span data-ttu-id="d8213-123">Usar expresiones en informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d8213-123">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
