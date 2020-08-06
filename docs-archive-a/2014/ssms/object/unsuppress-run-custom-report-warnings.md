---
title: Anular la supresión de las advertencias de Ejecutar informe personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: stevestein
ms.author: sstein
ms.openlocfilehash: 725362ff7f8a6c282529f652e8813a8083257eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743886"
---
# <a name="unsuppress-run-custom-report-warnings"></a><span data-ttu-id="5da5e-102">Anular la supresión de las advertencias de Ejecutar informe personalizado</span><span class="sxs-lookup"><span data-stu-id="5da5e-102">Unsuppress Run Custom Report Warnings</span></span>
  <span data-ttu-id="5da5e-103">Para los informes personalizados existen dos cuadros de diálogo de advertencia.</span><span class="sxs-lookup"><span data-stu-id="5da5e-103">There are two warning dialog boxes for custom reports.</span></span> <span data-ttu-id="5da5e-104">En este tema se describe cómo anular la supresión de la presentación de estos cuadros en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da5e-104">This topic describes how to unsuppress the display of these boxes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5da5e-105">De forma predeterminada, el cuadro de diálogo **Ejecutar informe personalizado** aparece antes de la ejecución de un informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="5da5e-105">By default, the **Run Custom Reports** dialog box appears before a custom report runs.</span></span> <span data-ttu-id="5da5e-106">Si activa la casilla **No volver a mostrar esta advertencia** , el cuadro de diálogo ya no aparecerá más.</span><span class="sxs-lookup"><span data-stu-id="5da5e-106">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span> <span data-ttu-id="5da5e-107">De forma predeterminada, el cuadro de diálogo **Ejecutar informe personalizado** también aparece cuando se abre un informe personalizado y, a continuación, se hace clic en un vínculo para abrir otro informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="5da5e-107">Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then click a link to open another custom report.</span></span> <span data-ttu-id="5da5e-108">Este cuadro de diálogo muestra la ruta completa al archivo de informe detallado personalizado.</span><span class="sxs-lookup"><span data-stu-id="5da5e-108">This dialog box displays the fill path to the drill-through custom report file.</span></span> <span data-ttu-id="5da5e-109">Si activa la casilla **No volver a mostrar esta advertencia** , el cuadro de diálogo ya no aparecerá más.</span><span class="sxs-lookup"><span data-stu-id="5da5e-109">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5da5e-110">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5da5e-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a><span data-ttu-id="5da5e-111">Para anular la supresión del cuadro de diálogo de advertencia principal del informe personalizado</span><span class="sxs-lookup"><span data-stu-id="5da5e-111">To unsuppress the main custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="5da5e-112">Conéctese al \<*Server*> \\ < *recurso compartido* >| \<*Drive*> \Documents and Settings \\<userprofile \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="5da5e-112">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="5da5e-113">Haga clic con el botón secundario `reports.xml` y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5da5e-113">Right-click `reports.xml`, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="5da5e-114">Cambie\*\* \<SuppressWarning> true \</SuppressWarning> a \<SuppressWarning> false \</SuppressWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="5da5e-114">Change**\<SuppressWarning>true\</SuppressWarning> to \<SuppressWarning>false\</SuppressWarning>**.</span></span>  
  
4.  <span data-ttu-id="5da5e-115">Reinicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da5e-115">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a><span data-ttu-id="5da5e-116">Para anular la supresión del cuadro de diálogo de advertencia del informe de obtención de detalles personalizado</span><span class="sxs-lookup"><span data-stu-id="5da5e-116">To unsuppress the drill-through custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="5da5e-117">Conéctese al \<*Server*> \\ < *recurso compartido* >| \<*Drive*> \Documents and Settings \\<userprofile \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="5da5e-117">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="5da5e-118">Haga clic con el botón secundario `reports.xml` y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5da5e-118">Right-click `reports.xml`, and click **Edit**.</span></span>  
  
3.  <span data-ttu-id="5da5e-119">Cambie \*\* \<SuppressDrillthroughWarning> true \</SuppressDrillthroughWarning> a \<SuppressDrillthroughWarning> false \</SuppressDrillthroughWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="5da5e-119">Change **\<SuppressDrillthroughWarning>true\</SuppressDrillthroughWarning>to \<SuppressDrillthroughWarning>false\</SuppressDrillthroughWarning>**.</span></span>  
  
4.  <span data-ttu-id="5da5e-120">Reinicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da5e-120">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da5e-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5da5e-121">See Also</span></span>  
 <span data-ttu-id="5da5e-122">[Informes personalizados en Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5da5e-122">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="5da5e-123">[Agregar un informe personalizado a Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5da5e-123">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="5da5e-124">Usar informes personalizados con las propiedades de nodo del Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5da5e-124">Use Custom Reports with Object Explorer Node Properties</span></span>](use-custom-reports-with-object-explorer-node-properties.md)  
  
  
