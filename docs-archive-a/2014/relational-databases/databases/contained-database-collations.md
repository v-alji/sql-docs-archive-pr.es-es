---
title: Intercalaciones de bases de datos independientes | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- contained database, collations
ms.assetid: 4b44f6b9-2359-452f-8bb1-5520f2528483
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2648dbedea7708c4f39c922c56bba96cf38b0c0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747027"
---
# <a name="contained-database-collations"></a><span data-ttu-id="b1e9a-102">Intercalaciones de bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="b1e9a-102">Contained Database Collations</span></span>
  <span data-ttu-id="b1e9a-103">Varias propiedades afectan a la semántica de igualdad y al criterio de ordenación de los datos de texto, como son la distinción entre mayúsculas y minúsculas y de los acentos, y el idioma básico que se usa.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-103">Various properties affect the sort order and equality semantics of textual data, including case sensitivity, accent sensitivity, and the base language being used.</span></span> <span data-ttu-id="b1e9a-104">Estas cualidades se expresan en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de la opción de intercalación de los datos.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-104">These qualities are expressed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the choice of collation for the data.</span></span> <span data-ttu-id="b1e9a-105">Para obtener una explicación más detallada de las intercalaciones, vea [Compatibilidad con la intercalación y Unicode](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="b1e9a-105">For a more in-depth discussion of collations themselves, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="b1e9a-106">Las intercalaciones se aplican no solo a los datos almacenados en las tablas de usuario, sino a todo el texto que se administra en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como son los metadatos, los objetos temporales, los nombres de variables, etc. Su tratamiento difiere en las bases de datos independientes y en las dependientes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-106">Collations apply not only to data stored in user tables, but to all text handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], including metadata, temporary objects, variable names, etc. The handling of these differs in contained and non-contained databases.</span></span> <span data-ttu-id="b1e9a-107">Este cambio no afectará a muchos usuarios, pero ayuda a proporcionar independencia de la instancia y uniformidad.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-107">This change will not affect many users, but helps provide instance independence and uniformity.</span></span> <span data-ttu-id="b1e9a-108">Pero esto también puede generar confusión, así como problemas en las sesiones que acceden tanto a bases de datos independientes como a bases de datos dependientes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-108">But this may also cause some confusion, as well as problems for sessions that access both contained and non-contained databases.</span></span>  
  
 <span data-ttu-id="b1e9a-109">Este tema clarifica el contenido del cambio y examina áreas en las que puede ocasionar problemas.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-109">This topic clarifies the content of the change, and examines areas where the change may cause problems.</span></span>  
  
## <a name="non-contained-databases"></a><span data-ttu-id="b1e9a-110">Bases de datos dependientes</span><span class="sxs-lookup"><span data-stu-id="b1e9a-110">Non-Contained Databases</span></span>  
 <span data-ttu-id="b1e9a-111">Todas las bases de datos tienen una intercalación predeterminada (que se puede establecer al crear o modificar una base de datos).</span><span class="sxs-lookup"><span data-stu-id="b1e9a-111">All databases have a default collation (which can be set when creating or altering a database.</span></span> <span data-ttu-id="b1e9a-112">Esta intercalación se usa para todos los metadatos de la base de datos, así como el valor predeterminado para todas las columnas de cadena dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-112">This collation is used for all metadata in the database, as well as the default for all string columns within the database.</span></span> <span data-ttu-id="b1e9a-113">Los usuarios pueden elegir una intercalación diferente para una columna en particular utilizando la cláusula `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-113">Users can choose a different collation for any particular column by using the `COLLATE` clause.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="b1e9a-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="b1e9a-114">Example 1</span></span>  
 <span data-ttu-id="b1e9a-115">Por ejemplo, si estuviéramos trabajando en Beijing, podríamos utilizar una intercalación china:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-115">For example, if we were working in Beijing, we might use a Chinese collation:</span></span>  
  
```sql  
ALTER DATABASE MyDB COLLATE Chinese_Simplified_Pinyin_100_CI_AS;  
```  
  
 <span data-ttu-id="b1e9a-116">Ahora, si creamos una columna, su intercalación predeterminada será esta intercalación china, pero podemos elegir otra si lo deseamos:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-116">Now if we create a column, its default collation will be this Chinese collation, but we can choose another one if we want:</span></span>  
  
```sql  
CREATE TABLE MyTable  
      (mycolumn1 nvarchar,  
      mycolumn2 nvarchar COLLATE Frisian_100_CS_AS);  
GO  
SELECT name, collation_name  
FROM sys.columns  
WHERE name LIKE 'mycolumn%' ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```sql  
name            collation_name  
--------------- ----------------------------------  
mycolumn1       Chinese_Simplified_Pinyin_100_CI_AS  
mycolumn2       Frisian_100_CS_AS  
```  
  
 <span data-ttu-id="b1e9a-117">Esto parece relativamente sencillo, pero surgen varios problemas.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-117">This appears relatively simple, but several problems arise.</span></span> <span data-ttu-id="b1e9a-118">Dado que la intercalación de una columna depende de la base de datos en la que se crea la tabla, surgen problemas con el uso de tablas temporales que se almacenan en `tempdb` .</span><span class="sxs-lookup"><span data-stu-id="b1e9a-118">Because the collation for a column is dependent on the database in which the table is created, problems arise with the use of temporary tables which are stored in `tempdb`.</span></span> <span data-ttu-id="b1e9a-119">La intercalación de `tempdb` normalmente coincide con la intercalación de la instancia, que no tiene que coincidir con la intercalación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-119">The collation of `tempdb` usually matches the collation for the instance, which does not have to match the database collation.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="b1e9a-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="b1e9a-120">Example 2</span></span>  
 <span data-ttu-id="b1e9a-121">Por ejemplo, considere la base de datos (chino) anterior cuando se usa en una instancia con una intercalación **Latin1_General** :</span><span class="sxs-lookup"><span data-stu-id="b1e9a-121">For example, consider the (Chinese) database above when used on an instance with a **Latin1_General** collation:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max)) ;  
GO  
```  
  
 <span data-ttu-id="b1e9a-122">A primera vista, estas dos tablas parecen como si tuvieran el mismo esquema, pero dado que las intercalaciones de las bases de datos difieren, los valores son en realidad incompatibles:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-122">At first glance, these two tables look like they have the same schema, but since the collations of the databases differ, the values are actually incompatible:</span></span>  
  
```  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="b1e9a-123">Mensaje 468, Nivel 16, Estado 9, Línea 2</span><span class="sxs-lookup"><span data-stu-id="b1e9a-123">Msg 468, Level 16, State 9, Line 2</span></span>  
  
 <span data-ttu-id="b1e9a-124">No puede resolver el conflicto de la intercalación entre "Latin1_General_100_CI_AS_KS_WS_SC" y Chinese_Simplified_Pinyin_100_CI_AS" en la operación igual que.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-124">Cannot resolve the collation conflict between "Latin1_General_100_CI_AS_KS_WS_SC" and Chinese_Simplified_Pinyin_100_CI_AS" in the equal to operation.</span></span>  
  
 <span data-ttu-id="b1e9a-125">Podemos corregir esto intercalando la tabla temporal explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-125">We can fix this by explicitly collating the temporary table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1e9a-126">facilita esto proporcionando la palabra clave `DATABASE_DEFAULT` para la cláusula `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-126">makes this somewhat easier by providing the `DATABASE_DEFAULT` keyword for the `COLLATE` clause.</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max) COLLATE DATABASE_DEFAULT);  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="b1e9a-127">Ahora esto se ejecuta sin error.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-127">This now runs without error.</span></span>  
  
 <span data-ttu-id="b1e9a-128">También podemos ver el comportamiento dependiente de la intercalación con variables.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-128">We can also see collation-dependent behavior with variables.</span></span> <span data-ttu-id="b1e9a-129">Considere la función siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-129">Consider the following function:</span></span>  
  
```  
CREATE FUNCTION f(@x INT) RETURNS INT  
AS BEGIN   
      DECLARE @I INT = 1  
      DECLARE @?? INT = 2  
      RETURN @x * @i  
END;  
```  
  
 <span data-ttu-id="b1e9a-130">Esta es una función bastante peculiar.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-130">This is a rather peculiar function.</span></span> <span data-ttu-id="b1e9a-131">En una intercalación que distingue entre mayúsculas y minúsculas, @i en la cláusula Return no puede enlazarse a @I ni @??.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-131">In a case-sensitive collation, the @i in the return clause cannot bind to either @I or @??.</span></span> <span data-ttu-id="b1e9a-132">En una intercalación Latin1_General sin distinción entre mayúsculas y minúsculas, @i enlaza a @I y la función devuelve 1.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-132">In a case-insensitive Latin1_General collation, @i binds to @I, and the function returns 1.</span></span> <span data-ttu-id="b1e9a-133">Pero en una intercalación turco sin distinción entre mayúsculas y minúsculas, @i se enlaza a @??, y la función devuelve 2.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-133">But in a case-insensitive Turkish collation, @i binds to @??, and the function returns 2.</span></span> <span data-ttu-id="b1e9a-134">Esto puede causar confusión en una base de datos que se mueva entre instancias con intercalaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-134">This can wreak havoc on a database that moves between instances with different collations.</span></span>  
  
## <a name="contained-databases"></a><span data-ttu-id="b1e9a-135">Bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="b1e9a-135">Contained Databases</span></span>  
 <span data-ttu-id="b1e9a-136">Dado que uno de los objetivos de diseño de las bases de datos independientes es hacer que sean autodependientes, la dependencia de las intercalaciones de `tempdb` e instancia debe romperse.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-136">Since a design objective of contained databases is to make them self-contained, the dependence on the instance and `tempdb` collations must be severed.</span></span> <span data-ttu-id="b1e9a-137">Para ello, las bases de datos independientes presentan el concepto de intercalación de catálogo.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-137">To do this, contained databases introduce the concept of the catalog collation.</span></span> <span data-ttu-id="b1e9a-138">La intercalación de catálogo se utiliza para los objetos transitorios y los metadatos del sistema.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-138">The catalog collation is used for system metadata and transient objects.</span></span> <span data-ttu-id="b1e9a-139">Abajo se proporcionan los detalles.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-139">Details are provided below.</span></span>  
  
 <span data-ttu-id="b1e9a-140">En una base de datos independiente, la intercalación de catálogo es **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-140">In a contained database, the catalog collation **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="b1e9a-141">Esta intercalación es la misma para todas las bases de datos independientes en todas las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-141">This collation is the same for all contained databases on all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot be changed.</span></span>  
  
 <span data-ttu-id="b1e9a-142">La intercalación de la base de datos se conserva, pero solo se usa como intercalación predeterminada para los datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-142">The database collation is retained, but is only used as the default collation for user data.</span></span> <span data-ttu-id="b1e9a-143">De forma predeterminada, la intercalación de la base de datos es igual a la de la base de datos del modelo, pero el usuario puede cambiarla a través de un `CREATE` `ALTER DATABASE` comando o como con las bases de datos dependientes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-143">By default, the database collation is equal to the model database collation, but can be changed by the user through a `CREATE` or `ALTER DATABASE` command as with non-contained databases.</span></span>  
  
 <span data-ttu-id="b1e9a-144">Una palabra clave nueva, `CATALOG_DEFAULT`, está disponible en la cláusula `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-144">A new keyword, `CATALOG_DEFAULT`, is available in the `COLLATE` clause.</span></span> <span data-ttu-id="b1e9a-145">Esto se utiliza como acceso directo a la intercalación actual de los metadatos tanto en las bases de datos independientes como en las dependientes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-145">This is used as a shortcut to the current collation of metadata in both contained and non-contained databases.</span></span> <span data-ttu-id="b1e9a-146">Es decir, en una base de datos dependiente, `CATALOG_DEFAULT` devolverá la intercalación de la base de datos actual, dado que los metadatos se intercalan en la intercalación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-146">That is, in a non-contained database, `CATALOG_DEFAULT` will return the current database collation, since metadata is collated in the database collation.</span></span> <span data-ttu-id="b1e9a-147">En una base de datos independiente, estos dos valores pueden ser diferentes, porque el usuario puede cambiar la intercalación de la base de datos para que no coincida con la del catálogo.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-147">In a contained database, these two values may be different, since the user can change the database collation so that it does not match the catalog collation.</span></span>  
  
 <span data-ttu-id="b1e9a-148">El comportamiento de varios objetos tanto en las bases de datos independientes como en las dependientes se resume en esta tabla:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-148">The behavior of various objects in both non-contained and contained databases is summarized in this table:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="b1e9a-149">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="b1e9a-149">**Item**</span></span>|<span data-ttu-id="b1e9a-150">**Base de datos dependiente**</span><span class="sxs-lookup"><span data-stu-id="b1e9a-150">**Non-Contained Database**</span></span>|<span data-ttu-id="b1e9a-151">**Base de datos independiente**</span><span class="sxs-lookup"><span data-stu-id="b1e9a-151">**Contained Database**</span></span>|  
|<span data-ttu-id="b1e9a-152">Datos del usuario (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b1e9a-152">User Data (default)</span></span>|<span data-ttu-id="b1e9a-153">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-153">DATABASE_DEFAULT</span></span>|<span data-ttu-id="b1e9a-154">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-154">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="b1e9a-155">Datos de Temp (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b1e9a-155">Temp Data (default)</span></span>|<span data-ttu-id="b1e9a-156">Intercalación de TempDB</span><span class="sxs-lookup"><span data-stu-id="b1e9a-156">TempDB Collation</span></span>|<span data-ttu-id="b1e9a-157">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-157">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="b1e9a-158">Metadatos</span><span class="sxs-lookup"><span data-stu-id="b1e9a-158">Metadata</span></span>|<span data-ttu-id="b1e9a-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span></span>|<span data-ttu-id="b1e9a-160">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-160">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="b1e9a-161">Metadatos temporales</span><span class="sxs-lookup"><span data-stu-id="b1e9a-161">Temporary Metadata</span></span>|<span data-ttu-id="b1e9a-162">Intercalación de TempDB</span><span class="sxs-lookup"><span data-stu-id="b1e9a-162">tempdb Collation</span></span>|<span data-ttu-id="b1e9a-163">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-163">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="b1e9a-164">variables</span><span class="sxs-lookup"><span data-stu-id="b1e9a-164">Variables</span></span>|<span data-ttu-id="b1e9a-165">Intercalación de instancia</span><span class="sxs-lookup"><span data-stu-id="b1e9a-165">Instance Collation</span></span>|<span data-ttu-id="b1e9a-166">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-166">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="b1e9a-167">Etiquetas Goto</span><span class="sxs-lookup"><span data-stu-id="b1e9a-167">Goto Labels</span></span>|<span data-ttu-id="b1e9a-168">Intercalación de instancia</span><span class="sxs-lookup"><span data-stu-id="b1e9a-168">Instance Collation</span></span>|<span data-ttu-id="b1e9a-169">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-169">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="b1e9a-170">Nombres de cursor</span><span class="sxs-lookup"><span data-stu-id="b1e9a-170">Cursor Names</span></span>|<span data-ttu-id="b1e9a-171">Intercalación de instancia</span><span class="sxs-lookup"><span data-stu-id="b1e9a-171">Instance Collation</span></span>|<span data-ttu-id="b1e9a-172">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b1e9a-172">CATALOG_DEFAULT</span></span>|  
  
 <span data-ttu-id="b1e9a-173">En el ejemplo de la tabla temporal descrito previamente, podemos ver que este comportamiento de la intercalación elimina la necesidad de una cláusula `COLLATE` explícita en la mayor parte de los usos de las tablas temporales.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-173">If we temp table example previously described, we can see that this collation behavior eliminates the need for an explicit `COLLATE` clause in most temp table uses.</span></span> <span data-ttu-id="b1e9a-174">En una base de datos independiente, este código se ejecuta ahora sin error, aun cuando las intercalaciones de instancia y base de datos difieren:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-174">In a contained database, this code now runs without error, even if the database and instance collations differ:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max));  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="b1e9a-175">Esto funciona porque `T1_txt` y `T2_txt` se intercalan en la intercalación de base de datos de la base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-175">This works because both `T1_txt` and `T2_txt` are collated in the database collation of the contained database.</span></span>  
  
## <a name="crossing-between-contained-and-uncontained-contexts"></a><span data-ttu-id="b1e9a-176">Cruzar los contextos contenidos y no contenidos</span><span class="sxs-lookup"><span data-stu-id="b1e9a-176">Crossing Between Contained and Uncontained Contexts</span></span>  
 <span data-ttu-id="b1e9a-177">Siempre que una sesión de una base de datos independiente sigue siendo contenida, debe permanecer dentro de la base de datos a la que se conectó.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-177">As long as a session in a contained database remains contained, it must remain within the database to which it connected.</span></span> <span data-ttu-id="b1e9a-178">En este caso el comportamiento es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-178">In this case the behavior is very straightforward.</span></span> <span data-ttu-id="b1e9a-179">Pero si una sesión cruza de un contexto contenido a uno no contenido, el comportamiento se vuelve más complejo, porque los dos conjuntos de reglas deben unirse.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-179">But if a session crosses between contained and non-contained contexts, the behavior becomes more complex, since the two sets of rules must be bridged.</span></span> <span data-ttu-id="b1e9a-180">Esto puede ocurrir en una base de datos parcialmente independiente, ya que un usuario puede usar `USE` en otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-180">This can happen in a partially-contained database, since a user may `USE` to another database.</span></span> <span data-ttu-id="b1e9a-181">El siguiente principio administra la diferencia en las reglas de intercalación en este caso.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-181">In this case, the difference in collation rules is handled by the following principle.</span></span>  
  
-   <span data-ttu-id="b1e9a-182">La base de datos en la que el lote comienza determina el comportamiento de la intercalación de un lote.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-182">The collation behavior for a batch is determined by the database in which the batch begins.</span></span>  
  
 <span data-ttu-id="b1e9a-183">Observe que esta decisión se toma antes de que se ejecute ningún comando, incluso un `USE` inicial.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-183">Note that this decision is made before any commands are issued, including an initial `USE`.</span></span> <span data-ttu-id="b1e9a-184">Es decir, si un lote comienza en una base de datos independiente, pero el primer comando es un `USE` de una base de datos dependiente, el comportamiento de la intercalación contenida se seguirá usando para el lote.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-184">That is, if a batch begins in a contained database, but the first command is a `USE` to a non-contained database, the contained collation behavior will still be used for the batch.</span></span> <span data-ttu-id="b1e9a-185">Por tanto, una referencia a una variable, por ejemplo, puede tener varios resultados posibles:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-185">Given this, a reference to a variable, for example, may have multiple possible outcomes:</span></span>  
  
-   <span data-ttu-id="b1e9a-186">La referencia puede encontrar una coincidencia exactamente.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-186">The reference may find exactly one match.</span></span> <span data-ttu-id="b1e9a-187">En este caso, la referencia funcionará sin generar un error.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-187">In this case, the reference will work without error.</span></span>  
  
-   <span data-ttu-id="b1e9a-188">La referencia puede no encontrar una coincidencia en la intercalación actual donde hubiera otra antes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-188">The reference may not find a match in the current collation where there was one before.</span></span> <span data-ttu-id="b1e9a-189">Esto producirá un error que indica que la variable no existe, aunque en apariencia se creara.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-189">This will raise an error indicating that the variable does not exist, even though it was apparently created.</span></span>  
  
-   <span data-ttu-id="b1e9a-190">La referencia puede encontrar varias coincidencias que eran distintas originalmente.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-190">The reference may find multiple matches that were originally distinct.</span></span> <span data-ttu-id="b1e9a-191">Esto también producirá un error.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-191">This will also raise an error.</span></span>  
  
 <span data-ttu-id="b1e9a-192">Mostraremos esto con varios ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-192">We'll illustrate this with a few examples.</span></span> <span data-ttu-id="b1e9a-193">Para ello, suponemos que hay una base de datos independiente parcialmente denominada `MyCDB` con su intercalación de la base de datos establecida en la intercalación predeterminada, **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-193">For these we assume there is a partially-contained database named `MyCDB` with its database collation set to the default collation, **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="b1e9a-194">Suponemos que la intercalación de la instancia es `Latin1_General_100_CS_AS_WS_KS_SC`.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-194">We assume that the instance collation is `Latin1_General_100_CS_AS_WS_KS_SC`.</span></span> <span data-ttu-id="b1e9a-195">Las dos intercalaciones solo difieren en la distinción de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-195">The two collations differ only in case sensitivity.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="b1e9a-196">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="b1e9a-196">Example 1</span></span>  
 <span data-ttu-id="b1e9a-197">El siguiente ejemplo ilustra el caso en el que la referencia encuentra exactamente una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-197">The following example illustrates the case where the reference finds exactly one match.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #a VALUES(1);  
GO  
  
USE master;  
GO  
  
SELECT * FROM #a;  
GO  
  
Results:  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
x  
-----------  
1  
```  
  
 <span data-ttu-id="b1e9a-198">En este caso, el #a identificado enlaza en la intercalación del catálogo sin distinción entre mayúsculas y minúsculas y la intercalación de la instancia con distinción entre mayúsculas y minúsculas, y el código se ejecuta bien.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-198">In this case, the identified #a binds in both the case-insensitive catalog collation and the case-sensitive instance collation, and the code works.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="b1e9a-199">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="b1e9a-199">Example 2</span></span>  
 <span data-ttu-id="b1e9a-200">En el siguiente ejemplo se ilustra el caso en el que la referencia no encuentra una coincidencia en la intercalación actual donde antes había una.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-200">The following example illustrates the case where the reference does not find a match in the current collation where there was one before.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #A VALUES(1);  
GO  
```  
  
 <span data-ttu-id="b1e9a-201">Aquí, #A enlaza a #a en la intercalación predeterminada sin distinción entre mayúsculas y minúsculas, y la inserción funciona,</span><span class="sxs-lookup"><span data-stu-id="b1e9a-201">Here, the #A binds to #a in the case-insensitive default collation, and the insert works,</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="b1e9a-202">Pero si continuamos el script...</span><span class="sxs-lookup"><span data-stu-id="b1e9a-202">But if we continue the script...</span></span>  
  
```  
USE master;  
GO  
  
SELECT * FROM #A;  
GO  
```  
  
 <span data-ttu-id="b1e9a-203">Obtenemos un error al intentar enlazar #A en la intercalación de la instancia con distinción entre mayúsculas y minúsculas;</span><span class="sxs-lookup"><span data-stu-id="b1e9a-203">We get an error trying to bind to #A in the case-sensitive instance collation;</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="b1e9a-204">Mensaje 208, Nivel 16, Estado 0, Línea 2</span><span class="sxs-lookup"><span data-stu-id="b1e9a-204">Msg 208, Level 16, State 0, Line 2</span></span>  
  
 <span data-ttu-id="b1e9a-205">El nombre de objeto '#A' no es válido.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-205">Invalid object name '#A'.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="b1e9a-206">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="b1e9a-206">Example 3</span></span>  
 <span data-ttu-id="b1e9a-207">El siguiente ejemplo ilustra el caso en el que la referencia encuentra varias coincidencias que eran distintas originalmente.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-207">The following example illustrates the case where the reference finds multiple matches that were originally distinct.</span></span> <span data-ttu-id="b1e9a-208">Primero, comenzamos en `tempdb` (que tiene la misma intercalación que distingue mayúsculas de minúsculas que nuestra instancia) y ejecutamos las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-208">First, we start in `tempdb` (which has the same case-sensitive collation as our instance) and execute the following statements.</span></span>  
  
```  
USE tempdb;  
GO  
  
CREATE TABLE #a(x int);  
GO  
CREATE TABLE #A(x int);  
GO  
INSERT INTO #a VALUES(1);  
GO  
INSERT INTO #A VALUES(2);  
GO  
```  
  
 <span data-ttu-id="b1e9a-209">Se ejecuta correctamente, dado que las tablas son distintas en esta intercalación:</span><span class="sxs-lookup"><span data-stu-id="b1e9a-209">This succeeds, since the tables are distinct in this collation:</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="b1e9a-210">Sin embargo, si pasamos a nuestra base de datos independiente, encontramos que ya no podemos enlazar a estas tablas.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-210">If we move into our contained database, however, we find that we can no longer bind to these tables.</span></span>  
  
```  
USE MyCDB;  
GO  
SELECT * FROM #a;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="b1e9a-211">Mensaje 12800, Nivel 16, Estado 1, Línea 2</span><span class="sxs-lookup"><span data-stu-id="b1e9a-211">Msg 12800, Level 16, State 1, Line 2</span></span>  
  
 <span data-ttu-id="b1e9a-212">La referencia al nombre de la tabla temporal '#a' es ambiguo y no se puede resolver.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-212">The reference to temp table name '#a' is ambiguous and cannot be resolved.</span></span> <span data-ttu-id="b1e9a-213">Los posibles candidatos son '#a' y '#A'.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-213">Possible candidates are '#a' and '#A'.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="b1e9a-214">Conclusión</span><span class="sxs-lookup"><span data-stu-id="b1e9a-214">Conclusion</span></span>  
 <span data-ttu-id="b1e9a-215">El comportamiento de la intercalación de bases de datos independientes difiere sutilmente del comportamiento en las bases de datos dependientes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-215">The collation behavior of contained databases differs subtly from that in non-contained databases.</span></span> <span data-ttu-id="b1e9a-216">Este comportamiento suele ser beneficioso y proporciona independencia de la instancia y simplicidad.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-216">This behavior is generally beneficial, providing instance-independence and simplicity.</span></span> <span data-ttu-id="b1e9a-217">Algunos usuarios pueden tener problemas, en concreto cuando una sesión accede tanto a bases de datos independientes como a dependientes.</span><span class="sxs-lookup"><span data-stu-id="b1e9a-217">Some users may have issues, particularly when a session accesses both contained and non-contained databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e9a-218">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1e9a-218">See Also</span></span>  
 [<span data-ttu-id="b1e9a-219">Bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="b1e9a-219">Contained Databases</span></span>](contained-databases.md)  
  
  
