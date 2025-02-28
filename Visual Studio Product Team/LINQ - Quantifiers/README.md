# LINQ - Quantifiers
## Requires
- Visual Studio 2010
## License
- Custom
## Technologies
- LINQ
## Topics
- Quantifiers
## Updated
- 08/12/2011
## Description

<table border="0" cellspacing="2" cellpadding="1" width="100%">
<tbody>
<tr align="left" valign="top">
<td align="left" valign="middle" style="background-color:#c0c0c0"><span style="color:#ffffff; font-size:x-large">&nbsp;Part of the 101 LINQ SAMPLES</span></td>
</tr>
</tbody>
</table>
<div class="RoundedBox">
<div class="boxheader">
<div class="BostonPostCard"></div>
</div>
<div class="boxheader"><span style="font-size:medium; background-color:#ffffff; color:#333333">Learn how to use LINQ in your applications with these code samples, covering the entire range of LINQ functionality and demonstrating LINQ with SQL, DataSets, and
 XML.</span></div>
<div class="boxcontent">
<table border="0" cellspacing="2" cellpadding="1" width="100%">
<tbody>
<tr align="left" valign="top">
<td width="50px" align="left" valign="middle"><a href="http://archive.msdn.microsoft.com/vb2008samples/Release/ProjectReleases.aspx?ReleaseId=1426"><img title="101 Samples for Visual Basic 2005" src="http://i.msdn.microsoft.com/dd183105.download_45(en-us,MSDN.10).jpg" alt="101 Samples for Visual Basic 2005" align="left"></a></td>
<td align="left" valign="middle"><span style="font-size:medium"><strong><a href="http://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b/viewsamplepack">Browse all 101 LINQ Samples</a>&nbsp;</strong></span></td>
</tr>
</tbody>
</table>
</div>
<hr>
<h1 id="Introduction">Introduction</h1>
<p>This sample shows different uses of Quantifiers:</p>
<ul class="bulletedlist">
<li><a href="#AnySimple">Any - Simple</a> </li><li><a href="#AnyGrouped">Any - Grouped</a> </li><li><a href="#AllSimple">All - Simple</a> </li><li><a href="#AllGrouped">All - Grouped</a> </li></ul>
<h1><span>Building the Sample</span></h1>
<ol>
<li>Open the Program.cs </li><li>Comment or uncomment the desired samples </li><li>Press Ctrl &#43; F5 </li></ol>
<h1>Description</h1>
<div class="fullwidth">
<div class="BostonPostCard">
<h2 id="AnySimple">Any - Simple</h2>
<p><span style="font-size:x-small">(<a href="#Introduction">back to top</a>)</span></p>
<p>This sample uses Any to determine if any of the words in the array contain the substring 'ei'.</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">csharp</span>

<div class="preview">
<pre class="csharp"><span class="cs__keyword">public</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;Linq67()&nbsp;
{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">string</span>[]&nbsp;words&nbsp;=&nbsp;{&nbsp;<span class="cs__string">&quot;believe&quot;</span>,&nbsp;<span class="cs__string">&quot;relief&quot;</span>,&nbsp;<span class="cs__string">&quot;receipt&quot;</span>,&nbsp;<span class="cs__string">&quot;field&quot;</span>&nbsp;};&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">bool</span>&nbsp;iAfterE&nbsp;=&nbsp;words.Any(w&nbsp;=&gt;&nbsp;w.Contains(<span class="cs__string">&quot;ei&quot;</span>));&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="cs__string">&quot;There&nbsp;is&nbsp;a&nbsp;word&nbsp;that&nbsp;contains&nbsp;in&nbsp;the&nbsp;list&nbsp;that&nbsp;contains&nbsp;'ei':&nbsp;{0}&quot;</span>,&nbsp;iAfterE);&nbsp;
}</pre>
</div>
</div>
</div>
<h3><strong>Result</strong></h3>
<p style="padding-left:30px"><code>There is a word that contains in the list that contains 'ei': True</code></p>
<p>&nbsp;</p>
<h2 id="AnyGrouped">Any - Grouped</h2>
<p><span style="font-size:x-small">(<a href="#Introduction">back to top</a>)</span></p>
<p>This sample uses Any to return a grouped a list of products only for categories that have at least one product that is out of stock.</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>CSS</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">css</span>

<div class="preview">
<pre class="css"><span class="css__element">public</span>&nbsp;<span class="css__element">void</span>&nbsp;<span class="css__element">Linq69</span>()&nbsp;
{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;List&lt;Product&gt;&nbsp;products&nbsp;=&nbsp;GetProductList();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;productGroups&nbsp;=&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;from&nbsp;p&nbsp;in&nbsp;products&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;group&nbsp;p&nbsp;by&nbsp;p.Category&nbsp;into&nbsp;g&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;where&nbsp;g.Any(p&nbsp;=&gt;&nbsp;p.UnitsInStock&nbsp;==&nbsp;<span class="css__number">0</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;select&nbsp;new&nbsp;{&nbsp;Category&nbsp;=&nbsp;g.Key,&nbsp;Products&nbsp;=&nbsp;g&nbsp;};&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="css__element">ObjectDumper</span><span class="css__class">.Write</span>(<span class="css__element">productGroups</span>,&nbsp;<span class="css__element">1</span>);&nbsp;&nbsp;
}</pre>
</div>
</div>
</div>
<h3><strong>Result</strong></h3>
<p style="padding-left:30px">Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=3&nbsp;&nbsp;ProductName=Aniseed Syrup&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=10.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=13&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=4&nbsp;&nbsp;ProductName=Chef Anton's Cajun Seasoning&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=22.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=53&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=5&nbsp;&nbsp;ProductName=Chef Anton's Gumbo Mix&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=21.3500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=0&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=6&nbsp;&nbsp;ProductName=Grandma's Boysenberry Spread&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=25.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=120&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=8&nbsp;&nbsp;ProductName=Northwoods Cranberry Sauce&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=40.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=6&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=15&nbsp;&nbsp;ProductName=Genen Shouyu&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=15.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=39&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=44&nbsp;&nbsp;ProductName=Gula Malacca&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=19.4500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=27&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=61&nbsp;&nbsp;ProductName=Sirop d'&Atilde;&copy;rable&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=28.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=113&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=63&nbsp;&nbsp;ProductName=Vegie-spread&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=43.9000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=24&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=65&nbsp;&nbsp;ProductName=Louisiana Fiery Hot Pepper Sauce&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=21.0500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=76&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=66&nbsp;&nbsp;ProductName=Louisiana Hot Spiced Okra&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=17.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=4&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=77&nbsp;&nbsp;ProductName=Original Frankfurter gr&Atilde;&frac14;ne So&Atilde;&Yuml;e&nbsp;&nbsp;&nbsp;&nbsp;Category=Condiments&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=13.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=32&nbsp;<br>
Category=Meat/Poultry&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=9&nbsp;&nbsp;ProductName=Mishi Kobe Niku&nbsp;&nbsp;&nbsp;&nbsp;Category=Meat/Poultry&nbsp;&nbsp;UnitPrice=97.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=29&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=17&nbsp;&nbsp;ProductName=Alice Mutton&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Meat/Poultry&nbsp;&nbsp;UnitPrice=39.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=0&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=29&nbsp;&nbsp;ProductName=Th&Atilde;&frac14;ringer Rostbratwurst&nbsp;&nbsp;&nbsp;&nbsp;Category=Meat/Poultry&nbsp;&nbsp;UnitPrice=123.7900&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=0&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=53&nbsp;&nbsp;ProductName=Perth Pasties&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Meat/Poultry&nbsp;&nbsp;UnitPrice=32.8000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=0&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=54&nbsp;&nbsp;ProductName=Tourti&Atilde;&uml;re&nbsp;&nbsp;Category=Meat/Poultry&nbsp;&nbsp;UnitPrice=7.4500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=21&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=55&nbsp;&nbsp;ProductName=P&Atilde;&cent;t&Atilde;&copy; chinois&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Meat/Poultry&nbsp;&nbsp;UnitPrice=24.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=115&nbsp;<br>
Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=11&nbsp;&nbsp;ProductName=Queso Cabrales&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=21.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=22&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=12&nbsp;&nbsp;ProductName=Queso Manchego La Pastora&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=38.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=86&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=31&nbsp;&nbsp;ProductName=Gorgonzola Telino&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=12.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=0&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=32&nbsp;&nbsp;ProductName=Mascarpone Fabioli&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=32.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=9&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=33&nbsp;&nbsp;ProductName=Geitost&nbsp;&nbsp;&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=2.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=112&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=59&nbsp;&nbsp;ProductName=Raclette Courdavault&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=55.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=79&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=60&nbsp;&nbsp;ProductName=Camembert Pierrot&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=34.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=19&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=69&nbsp;&nbsp;ProductName=Gudbrandsdalsost&nbsp;&nbsp;&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=36.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=26&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=71&nbsp;&nbsp;ProductName=Flotemysost&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=21.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=26&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=72&nbsp;&nbsp;ProductName=Mozzarella di Giovanni&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Dairy Products&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=34.8000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=14</p>
<p style="padding-left:30px">&nbsp;</p>
<h2 id="AllSimple">All - Simple</h2>
<p><span style="font-size:x-small">(<a href="#Introduction">back to top</a>)</span></p>
<p>This sample uses All to determine whether an array contains only odd numbers.</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">csharp</span>

<div class="preview">
<pre class="csharp"><span class="cs__keyword">public</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;Linq70()&nbsp;
{&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">int</span>[]&nbsp;numbers&nbsp;=&nbsp;{&nbsp;<span class="cs__number">1</span>,&nbsp;<span class="cs__number">11</span>,&nbsp;<span class="cs__number">3</span>,&nbsp;<span class="cs__number">19</span>,&nbsp;<span class="cs__number">41</span>,&nbsp;<span class="cs__number">65</span>,&nbsp;<span class="cs__number">19</span>&nbsp;};&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">bool</span>&nbsp;onlyOdd&nbsp;=&nbsp;numbers.All(n&nbsp;=&gt;&nbsp;n&nbsp;%&nbsp;<span class="cs__number">2</span>&nbsp;==&nbsp;<span class="cs__number">1</span>);&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(<span class="cs__string">&quot;The&nbsp;list&nbsp;contains&nbsp;only&nbsp;odd&nbsp;numbers:&nbsp;{0}&quot;</span>,&nbsp;onlyOdd);&nbsp;
}</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;<span style="font-size:12px; font-weight:bold"><strong>Result</strong></span></div>
<p>&nbsp;</p>
<p style="padding-left:30px"><code>The list contains only odd numbers: True</code></p>
<p>&nbsp;</p>
<h2 id="AllGrouped">All - Grouped</h2>
<p><span style="font-size:x-small">(<a href="#Introduction">back to top</a>)</span></p>
<p>This sample uses All to return a grouped a list of products only for categories that have all of their products in stock.</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">csharp</span>

<div class="preview">
<pre class="js">public&nbsp;<span class="js__operator">void</span>&nbsp;Linq72()&nbsp;
<span class="js__brace">{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;List&lt;Product&gt;&nbsp;products&nbsp;=&nbsp;GetProductList();&nbsp;
&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="js__statement">var</span>&nbsp;productGroups&nbsp;=&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;from&nbsp;p&nbsp;<span class="js__operator">in</span>&nbsp;products&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;group&nbsp;p&nbsp;by&nbsp;p.Category&nbsp;into&nbsp;g&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;where&nbsp;g.All(p&nbsp;=&gt;&nbsp;p.UnitsInStock&nbsp;&gt;&nbsp;<span class="js__num">0</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;select&nbsp;<span class="js__operator">new</span>&nbsp;<span class="js__brace">{</span>&nbsp;Category&nbsp;=&nbsp;g.Key,&nbsp;Products&nbsp;=&nbsp;g&nbsp;<span class="js__brace">}</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;ObjectDumper.Write(productGroups,&nbsp;<span class="js__num">1</span>);&nbsp;
<span class="js__brace">}</span></pre>
</div>
</div>
</div>
<h3><strong>Result</strong></h3>
<p style="padding-left:30px">Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=1&nbsp;&nbsp;ProductName=Chai&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=18.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=39&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=2&nbsp;&nbsp;ProductName=Chang&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=19.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=17&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=24&nbsp;&nbsp;ProductName=Guaran&Atilde;&iexcl; Fant&Atilde;&iexcl;stica&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=4.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=20&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=34&nbsp;&nbsp;ProductName=Sasquatch Ale&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=14.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=111&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=35&nbsp;&nbsp;ProductName=Steeleye Stout&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=18.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=20&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=38&nbsp;&nbsp;ProductName=C&Atilde;&acute;te de Blaye&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=263.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=17&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=39&nbsp;&nbsp;ProductName=Chartreuse verte&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=18.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=69&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=43&nbsp;&nbsp;ProductName=Ipoh Coffee&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=46.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=17&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=67&nbsp;&nbsp;ProductName=Laughing Lumberjack Lager&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=14.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=52&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=70&nbsp;&nbsp;ProductName=Outback Lager&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=15.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=15&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=75&nbsp;&nbsp;ProductName=Rh&Atilde;&para;nbr&Atilde;&curren;u Klosterbier&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=7.7500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=125&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=76&nbsp;&nbsp;ProductName=Lakkalik&Atilde;&para;&Atilde;&para;ri&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Beverages&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=18.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=57&nbsp;<br>
Category=Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=7&nbsp;&nbsp;ProductName=Uncle Bob's Organic Dried Pears&nbsp;&nbsp;&nbsp;&nbsp;Category=Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=30.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=15&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=14&nbsp;&nbsp;ProductName=Tofu&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=23.2500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=35&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=28&nbsp;&nbsp;ProductName=R&Atilde;&para;ssle Sauerkraut&nbsp;&nbsp;Category=Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=45.6000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=26&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=51&nbsp;&nbsp;ProductName=Manjimup Dried Apples&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=53.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=20&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=74&nbsp;&nbsp;ProductName=Longlife Tofu&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=10.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=4&nbsp;<br>
Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=10&nbsp;&nbsp;ProductName=Ikura&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=31.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=31&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=13&nbsp;&nbsp;ProductName=Konbu&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=6.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=24&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=18&nbsp;&nbsp;ProductName=Carnarvon Tigers&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=62.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=42&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=30&nbsp;&nbsp;ProductName=Nord-Ost Matjeshering&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=25.8900&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=10&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=36&nbsp;&nbsp;ProductName=Inlagd Sill&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=19.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=112&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=37&nbsp;&nbsp;ProductName=Gravad lax&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=26.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=11&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=40&nbsp;&nbsp;ProductName=Boston Crab Meat&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=18.4000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=123&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=41&nbsp;&nbsp;ProductName=Jack's New England Clam Chowder&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=9.6500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=85&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=45&nbsp;&nbsp;ProductName=Rogede sild&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=9.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=5&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=46&nbsp;&nbsp;ProductName=Spegesild&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=12.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=95&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=58&nbsp;&nbsp;ProductName=Escargots de Bourgogne&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=13.2500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=62&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=73&nbsp;&nbsp;ProductName=R&Atilde;&para;d Kaviar&nbsp;&nbsp;Category=Seafood&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=15.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=101&nbsp;<br>
Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=16&nbsp;&nbsp;ProductName=Pavlova&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=17.4500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=29&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=19&nbsp;&nbsp;ProductName=Teatime Chocolate Biscuits&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=9.2000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=25&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=20&nbsp;&nbsp;ProductName=Sir Rodney's Marmalade&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=81.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=40&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=21&nbsp;&nbsp;ProductName=Sir Rodney's Scones&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=10.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=3&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=25&nbsp;&nbsp;ProductName=NuNuCa Nu&Atilde;&Yuml;-Nougat-Creme&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=14.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=76&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=26&nbsp;&nbsp;ProductName=Gumb&Atilde;&curren;r Gummib&Atilde;&curren;rchen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=31.2300&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=15&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=27&nbsp;&nbsp;ProductName=Schoggi Schokolade&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=43.9000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=49&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=47&nbsp;&nbsp;ProductName=Zaanse koeken&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=9.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=36&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=48&nbsp;&nbsp;ProductName=Chocolade&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=12.7500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=15&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=49&nbsp;&nbsp;ProductName=Maxilaku&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=20.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=10&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=50&nbsp;&nbsp;ProductName=Valkoinen suklaa&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=16.2500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=65&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=62&nbsp;&nbsp;ProductName=Tarte au sucre&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=49.3000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=17&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=68&nbsp;&nbsp;ProductName=Scottish Longbreads&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Confections&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=12.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=6&nbsp;<br>
Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Products=...&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=22&nbsp;&nbsp;ProductName=Gustaf's Kn&Atilde;&curren;ckebr&Atilde;&para;d&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=21.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=104&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=23&nbsp;&nbsp;ProductName=Tunnbr&Atilde;&para;d&nbsp;&nbsp;&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=9.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=61&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=42&nbsp;&nbsp;ProductName=Singaporean Hokkien Fried Mee&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=14.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=26&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=52&nbsp;&nbsp;ProductName=Filo Mix&nbsp;&nbsp;&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=7.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=38&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=56&nbsp;&nbsp;ProductName=Gnocchi di nonna Alice&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=38.0000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=21&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=57&nbsp;&nbsp;ProductName=Ravioli Angelo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=19.5000&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=36&nbsp;<br>
&nbsp;&nbsp;Products: ProductID=64&nbsp;&nbsp;ProductName=Wimmers gute Semmelkn&Atilde;&para;del&nbsp;&nbsp;Category=Grains/Cereals&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitPrice=33.2500&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UnitsInStock=22</p>
<div style="padding-left:30px"></div>
</div>
</div>
<p style="padding-left:30px">&nbsp;</p>
<p><span style="font-size:20px; font-weight:bold">Source Code Files</span></p>
<ul>
<li><a class="browseFile" href="sourcecode?fileId=23929&pathId=270087730">Program.cs</a>
</li></ul>
<h1><strong>101 LINQ Samples</strong></h1>
<ul>
<li><a href="../LINQ-Restriction-Operators-b15d29ca">Restriction Operators</a> </li><li><a href="../LINQ-to-DataSets-09787825">Projection Operators</a> </li><li><a href="../LINQ-Partitioning-Operators-c68aaccc">Partitioning Operators</a> </li><li><a href="../SQL-Ordering-Operators-050af19e">Ordering Operators</a> </li><li><a href="../LINQ-to-DataSets-Grouping-c62703ea">Grouping Operators</a> </li><li><a href="../LINQ-Set-Operators-374f34fe">Set Operators</a> </li><li><a href="../LINQ-Conversion-Operators-e4e59714">Conversion Operators</a> </li><li><a href="../LINQ-Element-Operators-0f3f12ce">Element Operators</a> </li><li><a href="../LINQ-Element-Operators-0f3f12ce">Generation Operators</a> </li><li><a href="../LINQ-Quantifiers-f00e7e3e">Quantifiers</a> </li><li><a href="../LINQ-Aggregate-Operators-c51b3869">Aggregate Operators</a> </li><li><a href="../LINQ-Miscellaneous-6b72bb2a">Miscellaneous Operators</a> </li><li><a href="../LINQ-to-DataSets-Custom-41738490">Custom Sequence Operators</a> </li><li><a href="../LINQ-Query-Execution-ce0d3b95">Query Execution</a> </li><li><a href="../LINQ-Join-Operators-dabef4e9">Join Operators</a> </li></ul>
<h1>More Information</h1>
<p>For more information, see:</p>
<ul>
<li>Quantifier Operations - <a href="http://msdn.microsoft.com/en-us/library/bb546128.aspx" target="_blank">
http://msdn.microsoft.com/en-us/library/bb546128.aspx</a> </li></ul>
</div>
