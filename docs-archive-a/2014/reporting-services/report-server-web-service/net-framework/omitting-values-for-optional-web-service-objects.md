---
title: Omitir valores para objetos de servicio web opcionales | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3858f73e1b332acfa1a1bbc640007f6f0884abff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745025"
---
# <a name="omitting-values-for-optional-web-service-objects"></a><span data-ttu-id="bfaba-102">Omitir valores para objetos de servicio web opcionales</span><span class="sxs-lookup"><span data-stu-id="bfaba-102">Omitting Values for Optional Web Service Objects</span></span>
  <span data-ttu-id="bfaba-103">Las propiedades de algunos de los tipos complejos del servicio web del servidor de informes tienen una propiedad acompañante conocida como la propiedad Specified.</span><span class="sxs-lookup"><span data-stu-id="bfaba-103">Properties of several of the Report Server Web service complex types have an accompanying property known as the Specified property.</span></span> <span data-ttu-id="bfaba-104">El nombre de la propiedad está compuesto del nombre de propiedad original con la palabra "Specified" anexada a él.</span><span class="sxs-lookup"><span data-stu-id="bfaba-104">The name of the property consists of the original property name with the word "Specified" appended to it.</span></span> <span data-ttu-id="bfaba-105">La presencia de esta propiedad indica que en ocasiones se puede omitir un valor para la propiedad original.</span><span class="sxs-lookup"><span data-stu-id="bfaba-105">The presence of this property indicates that a value for the original property may sometimes be omitted.</span></span> <span data-ttu-id="bfaba-106">Éste es un resultado directo de la traducción del lenguaje de descripción de servicios web (WSDL) a una clase de proxy [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfaba-106">This is a direct result of the translation from the Web Service Description Language (WSDL) to a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class.</span></span> <span data-ttu-id="bfaba-107">Por ejemplo, la propiedad del servicio web <xref:ReportService2010.DataSourceDefinition.Enabled%2A> del tipo complejo <xref:ReportService2010.DataSourceDefinition> tiene una propiedad acompañante denominada <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span><span class="sxs-lookup"><span data-stu-id="bfaba-107">For example, the Web service property <xref:ReportService2010.DataSourceDefinition.Enabled%2A> of the complex type <xref:ReportService2010.DataSourceDefinition> has an accompanying property named <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span></span> <span data-ttu-id="bfaba-108">Si está generando una aplicación y no desea establecer un valor para la propiedad <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, no tiene que proporcionar un valor para <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; se utiliza el valor predeterminado `true`.</span><span class="sxs-lookup"><span data-stu-id="bfaba-108">If you are building an application and do not want to set a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you do not have to supply a value for <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; the default value of `true` is used.</span></span> <span data-ttu-id="bfaba-109">Sin embargo, todavía necesita establecer <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="bfaba-109">However, you still need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> to `false`.</span></span> <span data-ttu-id="bfaba-110">Si proporciona un valor para la propiedad <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, debe establecer <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> igual a `true`.</span><span class="sxs-lookup"><span data-stu-id="bfaba-110">If you supply a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> equal to `true`.</span></span> <span data-ttu-id="bfaba-111">Éste es el caso para las propiedades en que se puede escribir.</span><span class="sxs-lookup"><span data-stu-id="bfaba-111">This is the case for writable properties.</span></span> <span data-ttu-id="bfaba-112">Para las propiedades de solo lectura, no necesita tomar ninguna medida.</span><span class="sxs-lookup"><span data-stu-id="bfaba-112">For read-only properties, you do not need to take any action.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bfaba-113">El error para especificar una propiedad mediante la técnica mencionada anteriormente puede producir un comportamiento del servicio web imprevisible.</span><span class="sxs-lookup"><span data-stu-id="bfaba-113">Failure to specify a property using the above-mentioned technique can result in unpredictable Web service behavior.</span></span>  
  
 <span data-ttu-id="bfaba-114">Los tipos de datos que normalmente requieren que se controlen las propiedades adicionales especificadas son `Boolean` , `DateTime` y `Enumeration` .</span><span class="sxs-lookup"><span data-stu-id="bfaba-114">The data types that usually require you to handle the additional Specified property are `Boolean`, `DateTime`, and `Enumeration`.</span></span>  
  
 <span data-ttu-id="bfaba-115">Para obtener un ejemplo, vea el método <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="bfaba-115">For an example, see <xref:ReportService2010.ReportingService2010.CreateDataSource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfaba-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bfaba-116">See Also</span></span>  
 <span data-ttu-id="bfaba-117">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="bfaba-117">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="bfaba-118">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bfaba-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
