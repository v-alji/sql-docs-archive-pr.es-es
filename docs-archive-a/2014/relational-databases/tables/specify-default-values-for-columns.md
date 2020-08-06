---
title: Especificar valores predeterminados para las columnas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 650347c29e1175c5a1fe646fc079478520dc8c6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675751"
---
# <a name="specify-default-values-for-columns"></a><span data-ttu-id="65fcf-102">Especificar valores predeterminados para las columnas</span><span class="sxs-lookup"><span data-stu-id="65fcf-102">Specify Default Values for Columns</span></span>
  <span data-ttu-id="65fcf-103">Puede especificar un valor predeterminado que se escribirá en la columna de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65fcf-103">You can specify a default value that will be entered in the column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="65fcf-104">Si no asigna un valor predeterminado y el usuario deja la columna en blanco, entonces:</span><span class="sxs-lookup"><span data-stu-id="65fcf-104">If you do not assign a default value and the user leaves the column blank, then:</span></span>  
  
-   <span data-ttu-id="65fcf-105">Si estableció la opción de permitir valores NULL, se insertará NULL en la columna.</span><span class="sxs-lookup"><span data-stu-id="65fcf-105">If you set the option to allow null values, NULL will be inserted into the column.</span></span>  
  
-   <span data-ttu-id="65fcf-106">Si no se establece la opción para permitir valores NULL, la columna permanecerá en blanco, pero el usuario no podrá guardar la fila hasta que especifique un valor para la columna.</span><span class="sxs-lookup"><span data-stu-id="65fcf-106">If you do not set the option to allow null values, the column will remain blank, but the user will not be able to save the row until they supply a value for the column.</span></span>  
  
 <span data-ttu-id="65fcf-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="65fcf-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="65fcf-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="65fcf-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65fcf-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="65fcf-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="65fcf-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="65fcf-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65fcf-111">**Para especificar un valor predeterminado con:**</span><span class="sxs-lookup"><span data-stu-id="65fcf-111">**To specify a default value, using:**</span></span>  
  
     [<span data-ttu-id="65fcf-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65fcf-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="65fcf-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65fcf-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65fcf-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="65fcf-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="65fcf-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="65fcf-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="65fcf-116">Si la entrada del campo **Valor predeterminado** reemplaza un valor predeterminado enlazado (que se muestra sin paréntesis), se le preguntará si quiere desenlazar el valor predeterminado y sustituirlo por el nuevo.</span><span class="sxs-lookup"><span data-stu-id="65fcf-116">If your entry in the **Default Value** field replaces a bound default (which is shown without parentheses), you will be prompted to unbind the default and replace it with your new default.</span></span>  
  
-   <span data-ttu-id="65fcf-117">Para escribir una cadena de texto, incluya el valor entre comillas simples ('); no debe usar comillas dobles (") porque están reservadas para los identificadores escritos entre comillas.</span><span class="sxs-lookup"><span data-stu-id="65fcf-117">To enter a text string, enclose the value in single quotation marks ('); do not use double quotation marks (") because they are reserved for quoted identifiers.</span></span>  
  
-   <span data-ttu-id="65fcf-118">Para especificar un valor predeterminado numérico, escriba el número sin comillas.</span><span class="sxs-lookup"><span data-stu-id="65fcf-118">To enter a numeric default, enter the number without quotation marks around it.</span></span>  
  
-   <span data-ttu-id="65fcf-119">Para especificar un objeto o función, escriba el nombre del objeto o función sin comillas.</span><span class="sxs-lookup"><span data-stu-id="65fcf-119">To enter an object/function, enter the name of the object/function without quotation marks around it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65fcf-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="65fcf-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="65fcf-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="65fcf-121">Permissions</span></span>  
 <span data-ttu-id="65fcf-122">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="65fcf-122">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="65fcf-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65fcf-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="65fcf-124">Para especificar un valor predeterminado para una columna</span><span class="sxs-lookup"><span data-stu-id="65fcf-124">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="65fcf-125">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla que contenga columnas cuya escala quiera cambiar y, después, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="65fcf-125">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="65fcf-126">Seleccione la columna para la que desea especificar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="65fcf-126">Select the column for which you want to specify a default value.</span></span>  
  
3.  <span data-ttu-id="65fcf-127">En la pestaña **Propiedades de columna** , escriba el nuevo valor predeterminado en la propiedad **Valor o enlace predeterminado** .</span><span class="sxs-lookup"><span data-stu-id="65fcf-127">In the **Column Properties** tab, enter the new default value in the **Default Value or Binding** property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65fcf-128">Para especificar un valor predeterminado numérico, escriba el número.</span><span class="sxs-lookup"><span data-stu-id="65fcf-128">To enter a numeric default value, enter the number.</span></span> <span data-ttu-id="65fcf-129">Para un objeto o función, escriba su nombre.</span><span class="sxs-lookup"><span data-stu-id="65fcf-129">For an object or function enter its name.</span></span> <span data-ttu-id="65fcf-130">Para un valor predeterminado alfanumérico escriba el valor entre comillas simples.</span><span class="sxs-lookup"><span data-stu-id="65fcf-130">For an alphanumeric default enter the value inside single quotes.</span></span>  
  
4.  <span data-ttu-id="65fcf-131">En el menú **Archivo**, haga clic en \***Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="65fcf-131">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="65fcf-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65fcf-132">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="65fcf-133">Para especificar un valor predeterminado para una columna</span><span class="sxs-lookup"><span data-stu-id="65fcf-133">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="65fcf-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65fcf-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="65fcf-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="65fcf-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="65fcf-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="65fcf-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 <span data-ttu-id="65fcf-137">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65fcf-137">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
