The following table lists teh search operators that work with the Google search service.

<details>

<summary>Web Search Service:</summary>

| Search Operator Syntax | Description |
| :---: | :--- |
| `allinanchor: <ARG-1> <ARG-2> ... <ARG-N>` | The sarch engine restricts to pages containing all query terms you specify in the <ins>anchor text</ins>. Anchor text is the text on a page that is linked to another webpage or a different place on the current page. When you click on anchor text, you will be taken to the page or place on the page to which it is likned. **When using this operator in a query, do not include any other search operators.** | 
| `allintext: <ARG-1> <ARG-2> ... <ARG-N>` |  Search engine restricts results to those containing all the query terms you specify in the text of the page. |
| `allintitle: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts to those containing all the query terms you specify in the <ins>title</ins>. The title of a webpage is usually displayed at the top of the browser windows. The author of a website specifies the title of a page with the HTML TITLE element. There's only one title in a webpage. **When using this operator in a query, do not inlcude any other search operators.** |
| `allinurl: <ARG-1> <ARG-2> ... <ARG-N>` | The search engine restricts results to those containing all the query terms you specify in the URL. In URLs, words are often run together. |
| `cache:URL <ARG-1> <ARG-2> ... <ARG-N>` | Will display the Search engine's cached version of a web page, instead of the current version of the page. |
| `define:` | The search engine shows definitions from pages on the web for the term that follows. This advanced search operator is useful for finding definitions of words, phrases, and acronyms. |
| `filetype:<ARG>` | The serach engine will restrict the results to pages whose name end in <ins>sufix</ins>. You can restrict the results by using the `OR` operator. |
| `id:` | This is an undocumented alias for `info:`. |
| `inanchor:<ARG>` | The search engine will restrict the results to pages containing the query terms you specify in the <ins>anchor text</ins> or links to the page. |
| `info:<URL>` | Will present some information about the corresponding web page. This information can also be obtained by typing the web page URL directly into a search engine search box. |
| `intext:<ARG>` | The search engine restricts results to documents containing <ins>term</ins> in the text. Putting `intext:` in front of every word in query is equivalent to putting `allintext:` at the front of you query. |
| `intitle:<ARG>` | The search engine restricts the results to documents containing <ins>term</ins> in the title. Putting `intitle:` in front of every word in your query is equivalent to putting `allintitle:` at the front of your query. |
| `inurl:<ARG>` | The search engine will restrict the results to documents containing that word in the <ins>URL</ins>. Putting `inurl:` in front of every word in your query is equivalent to putting `allinurl:` at the front of your query. In URLs, words are often run together. They need not be run together when you're using this operator. |
| `related:<URL>` | Will list web pages that are similar to the web page you specify. |
| `site:<DOMAIN>` | The search engine will restrict your search results to the site or domain you specify. You can use many of the search operators in conjunction with the basic search operators `+`.`-`,`OR` and `" "`. |

</details>
<details>

<summary>Image Search</summary>

| Search Operator | Description |
| :---: | :--- |
| `allintitle: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts to those containing all the query terms you specify in the <ins>title</ins>. The title of a webpage is usually displayed at the top of the browser windows. The author of a website specifies the title of a page with the HTML TITLE element. There's only one title in a webpage. **When using this operator in a query, do not inlcude any other search operators.** The operator will return images in files whose names contains the terms that you specify. |
| `allinurl: <ARG-1> <ARG-2> ... <ARG-N>` | The search engine restricts results to those containing all the query terms you specify in the URL. In URLs, words are often run together. |
| `filetype:<ARG>` | The serach engine will restrict the results to pages whose name end in <ins>sufix</ins>. You can restrict the results by using the `OR` operator. |
| `inurl:<ARG>` | The search engine will restrict the results to documents containing that word in the <ins>URL</ins>. Putting `inurl:` in front of every word in your query is equivalent to putting `allinurl:` at the front of your query. In URLs, words are often run together. They need not be run together when you're using this operator. |
| `intitle:<ARG>` | The search engine restricts the results to documents containing <ins>term</ins> in the title. Putting `intitle:` in front of every word in your query is equivalent to putting `allintitle:` at the front of your query. |
| `site:<DOMAIN>` | The search engine will restrict your search results to the site or domain you specify. You can use many of the search operators in conjunction with the basic search operators `+`.`-`,`OR` and `" "`. |

</details>
<details>

<summary>Groups</summary>

| Search Operator | Description |
| :---: | :--- |
| `allintext: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts results to those containing all the query terms you specify in the text of the page. |
| `allintitle: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts to those containing all the query terms you specify in the <ins>title</ins>. The title of a webpage is usually displayed at the top of the browser windows. The author of a website specifies the title of a page with the HTML TITLE element. There's only one title in a webpage. **When using this operator in a query, do not inlcude any other search operators.** |
| `author:<ARG>` | The search engine will restrict the Groups results to include newsgroup articles by the author you specify. The author can be a full or partial name or email address. |
| `group:<ARG-1>.<ARG-2>.<ARG-N>` | The search engine will restrict the results to newsgroup articles from certain groups or subareas. |
| `insubject:"< ARGs >"` | The search engine restricts articles in Groups to those that contain the terms you specify in the subject. Equivalent to `intitle:` operator. |
| `intext:` | The search engine restricts results to documents containing <ins>term</ins> in the text. Putting `intext:` in front of every word in query is equivalent to putting `allintext:` at the front of you query. |
| `intitle:<ARG>` | The search engine restricts the results to documents containing <ins>term</ins> in the title. Putting `intitle:` in front of every word in your query is equivalent to putting `allintitle:` at the front of your query. |

</details>
<details>

<summary>Directory</summary>

| Search Operator | Description |
| :---: | :--- |
| `allintext: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts results to those containing all the query terms you specify in the text of the page. |
| `allintitle: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts to those containing all the query terms you specify in the <ins>title</ins>. The title of a webpage is usually displayed at the top of the browser windows. The author of a website specifies the title of a page with the HTML TITLE element. There's only one title in a webpage. **When using this operator in a query, do not inlcude any other search operators.** |
| `allinurl: <ARG-1> <ARG-2> ... <ARG-N>` | The search engine restricts results to those containing all the query terms you specify in the URL. In URLs, words are often run together. |
| `ext:` | This is the undocumented alias for `filetype:` operator. |
| `filetype:<ARG>` | The serach engine will restrict the results to pages whose name end in <ins>sufix</ins>. You can restrict the results by using the `OR` operator. |
| `intext:` | The search engine restricts results to documents containing <ins>term</ins> in the text. Putting `intext:` in front of every word in query is equivalent to putting `allintext:` at the front of you query. |
| `intitle:<ARG>` | The search engine restricts the results to documents containing <ins>term</ins> in the title. Putting `intitle:` in front of every word in your query is equivalent to putting `allintitle:` at the front of your query. |
| `inrul:<ARG>` | The search engine will restrict the results to documents containing that word in the <ins>URL</ins>. Putting `inurl:` in front of every word in your query is equivalent to putting `allinurl:` at the front of your query. In URLs, words are often run together. They need not be run together when you're using this operator. |

</details>
<details>

<summary>News</summary>

| Search Operator | Description |
| :---: | :--- |
| `allintext: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts results to those containing all the query terms you specify in the text of the page. |
| `allintitle: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts to those containing all the query terms you specify in the <ins>title</ins>. The title of a webpage is usually displayed at the top of the browser windows. The author of a website specifies the title of a page with the HTML TITLE element. There's only one title in a webpage. **When using this operator in a query, do not inlcude any other search operators.** The operator will return articles whose titles include the terms you specify. |
| `allinurl: <ARG-1> <ARG-2> ... <ARG-N>` | The search engine restricts results to those containing all the query terms you specify in the URL. In URLs, words are often run together. Will return aritcles whose titles include the terms you specify. |
| `intext:` | The search engine restricts results to documents containing <ins>term</ins> in the text. Putting `intext:` in front of every word in query is equivalent to putting `allintext:` at the front of you query. |
| `intitle:<ARG>` | The search engine restricts the results to documents containing <ins>term</ins> in the title. Putting `intitle:` in front of every word in your query is equivalent to putting `allintitle:` at the front of your query. |
| `inurl:<ARG>` | The search engine will restrict the results to documents containing that word in the <ins>URL</ins>. Putting `inurl:` in front of every word in your query is equivalent to putting `allinurl:` at the front of your query. In URLs, words are often run together. They need not be run together when you're using this operator. |
| `location:<ARG>` | Only articles from the location you specify will be returned. Abreviations for countries also work. |
| `source:<ARG-1>_<ARG-2>_<ARG-N>` | Search engine will restrict the search to articles from the news source with the ID you specify. To find a news source ID, enter a query that includes a term and the name of the publication you're seeking. |

</details>
<details>

<summary>Product Search</summary>

| Search Operator | Description |
| :---: | :--- |
| `allintext: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts results to those containing all the query terms you specify in the text of the page. |
| `allintitle: <ARG-1> <ARG-2> ... <ARG-N>` | Search engine restricts to those containing all the query terms you specify in the <ins>title</ins>. The title of a webpage is usually displayed at the top of the browser windows. The author of a website specifies the title of a page with the HTML TITLE element. There's only one title in a webpage. **When using this operator in a query, do not inlcude any other search operators.** |

</details>
<details>

<summary>Uncategorized</summary>

| Search Operator | Description |
| :---: | :--- |
| `link:<URL>` | Shows pages that point to that URL. You cannot combine a `link:` search with a regular keyword search. |
| `movie: <ARG-1> <ARG-2> <ARG-N>` | The search engine will find movie-related information. |
| `whether <ARG-1> <ARG-2> <ARG-N>` | If you enter a query with this operator and a city or location, the search engine recognize the location, the forecast will appear at the top of the results page. Otherwise, your result will usually include links to sites with the weather conditions and forecast for that location. |

</details>

---

For information and reference the following links were used:
- [Google Guide Reference Page](https://www.googleguide.com/advanced_operators_reference.html "Advanced Google Search Operators")
- [Google Hacking Database](https://www.exploit-db.com/google-hacking-database)

---

You may use many of the basic operators and search opeators with each other. However, there are some that must be used by themselves and others that you should be careful about using together.

Search operators that <ins>cannot be combined</ins>
- All the search operators whose names being with "**allin**".
- Syntaxes that request special information, e.g. `define:`.
- Page-specific search operators, e.g., `cache:`, `info:`, `related:`.

Be careful about the effects of a search operator when you use more than one of them in a query.
- Do not use serach operators that will cancel each other.
- Take care not to exclude all results when using certain serach operators more than once in a query.
- Focus your search by using several search operators.
