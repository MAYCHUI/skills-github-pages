Bỏ qua nội dung chính
Tìm kiếm GitHub Docs
https://docs.github.com/en/site-policy/privacy-policies/github-subprocessorsBỏ qua nội dung chính Tài liệu GitHub Chính sách trang web /Chính sách bảo mật /Tuyên bố chung về quyền riêng tư của GitHub Tuyên bố chung về quyền riêng tư của GitHub Trong bài viết này Tuyên bố về quyền riêng tư của GitHub Chúng tôi thu thập những thông tin cá nhân nào Mục đích xử lý: cách chúng tôi sử dụng Dữ liệu cá nhân của bạn Chia sẻ dữ liệu cá nhân Kho lưu trữ riêng tư: truy cập GitHub Cơ sở pháp lý để xử lý Dữ liệu cá nhân 
Tìm kiếm GitHub /Tìm kiếm mã GitHub /Cú pháp tìm kiếm mã
Tổng quan về cú pháp tìm kiếm mã GitHub
Bạn có thể tạo truy vấn tìm kiếm cho kết quả bạn muốn bằng cách sử dụng các mã định danh chuyên dụng, biểu thức chính quy và phép toán Boolean.

Trong bài viết này
Về cấu trúc của truy vấn tìm kiếm mã
Truy vấn để tìm kết quả khớp chính xác
Tìm kiếm dấu ngoặc kép và dấu gạch chéo ngược
Sử dụng các phép toán Boolean
Sử dụng các từ hạn định
Sử dụng biểu thức chính quy
Phân tách các thuật ngữ tìm kiếm
Phân biệt chữ hoa chữ thường
Về cấu trúc của truy vấn tìm kiếm mã
Cú pháp tìm kiếm trong bài viết này chỉ áp dụng cho việc tìm kiếm mã bằng GitHub Code Search. Lưu ý rằng cú pháp và các tiêu chí để tìm kiếm nội dung không phải mã, chẳng hạn như sự cố, người dùng và thảo luận, không giống với cú pháp để tìm kiếm mã. Để biết thêm thông tin về tìm kiếm không phải mã, hãy xem Giới thiệu về tìm kiếm trên GitHub và Tìm kiếm trên GitHub .

Truy vấn tìm kiếm bao gồm các thuật ngữ tìm kiếm, bao gồm văn bản bạn muốn tìm kiếm và các yếu tố hạn chế giúp thu hẹp phạm vi tìm kiếm.

Một thuật ngữ không có từ hạn định sẽ khớp với nội dung của tệp hoặc đường dẫn của tệp.

Ví dụ, truy vấn sau:

http-push
Truy vấn trên sẽ khớp với tệp docs/http-push.txt, ngay cả khi nó không chứa thuật ngữ http-push. Nó cũng sẽ khớp với một tệp có tên example.txtnếu nó chứa thuật ngữ http-push.

Bạn có thể nhập nhiều thuật ngữ cách nhau bằng dấu cách để tìm kiếm tài liệu khớp với cả hai thuật ngữ.

Ví dụ, truy vấn sau:

sparse index
Kết quả tìm kiếm sẽ bao gồm tất cả các tài liệu có chứa các thuật ngữ sparsevà index, theo bất kỳ thứ tự nào. Ví dụ, nó sẽ khớp với một tệp chứa SparseIndexVector, một tệp có cụm từ index for sparse trees, và thậm chí một tệp có tên index.txtchứa thuật ngữ sparse.

Tìm kiếm nhiều thuật ngữ được phân tách bằng khoảng trắng tương đương với tìm kiếm hello AND world. Các phép toán Boolean khác, chẳng hạn như hello OR world, cũng được hỗ trợ. Để biết thêm thông tin về các phép toán Boolean, hãy xem Sử dụng các phép toán Boolean .

Tìm kiếm mã cũng hỗ trợ tìm kiếm một chuỗi chính xác, bao gồm cả khoảng trắng. Để biết thêm thông tin, hãy đọc Truy vấn để tìm kết quả khớp chính xác .

Bạn có thể thu hẹp phạm vi tìm kiếm mã của mình bằng các ký tự chuyên biệt, chẳng hạn như repo:, language:và path:. Để biết thêm thông tin về các từ hạn định mà bạn có thể sử dụng khi tìm kiếm mã, hãy xem Sử dụng từ hạn định .

También puedes usar expresiones regulares en las búsquedas rodeando la expresión con barras diagonales. Para obtener más información sobre el uso de expresiones regulares, consulta Uso de expresiones regulares.

Consulta de una coincidencia exacta
Para buscar una cadena exacta, incluido el espacio en blanco, puedes rodear la cadena con comillas. Por ejemplo:

"sparse index"
También puedes usar cadenas entre comillas en calificadores, por ejemplo:

path:git language:"protocol buffers"
Buscar comillas y barras diagonales inversas
Para buscar un código que contenga comillas, puedes establecer la comilla mediante una barra diagonal inversa. Por ejemplo, para buscar la cadena exacta name = "tensorflow", puedes buscar:

"name = \"tensorflow\""
Para buscar un código que contenga una barra diagonal inversa, \, use una barra diagonal inversa doble, \\.

Las dos secuencias de escape \\ y \" también se pueden usar fuera de comillas. Sin embargo, no se reconoce ninguna otra secuencia de escape. Una barra diagonal inversa que no va seguida de " o \ se incluye en la búsqueda, sin cambios.

Las secuencias de escape adicionales, como \n para que coincidan con un carácter de nueva línea, se admiten en expresiones regulares. Consulta Uso de expresiones regulares.

Uso de operaciones booleanas
La búsqueda de código admite expresiones booleanas. Puedes usar los operadores AND, OR y NOT para combinar términos de búsqueda.

De forma predeterminada, los términos adyacentes separados por espacios en blanco son equivalentes al uso del operador AND. Por ejemplo, la consulta de búsqueda sparse index es la misma que sparse AND index, lo que significa que los resultados de la búsqueda incluirán todos los documentos que contengan los términos sparse y index, en cualquier orden.

Para buscar documentos que contengan un término u otro, puedes usar el operador OR. Por ejemplo, la consulta siguiente coincidirá con los documentos que contengan sparse o index:

sparse OR index
Para excluir archivos de los resultados de búsqueda, puedes usar el operador NOT. Por ejemplo, para excluir archivos en el directorio __testing__, puedes buscar:

"fatal error" NOT path:__testing__
Puedes usar paréntesis para expresar expresiones booleanas más complicadas. Por ejemplo:

(language:ruby OR language:python) AND NOT path:"/tests/"
Uso de calificadores
Puedes usar palabras clave especializadas para calificar la búsqueda.

Calificador de repositorio
Calificadores de organización y usuario
Calificador de lenguaje
Calificador de ruta de acceso
Calificador de símbolos
Calificador de contenido
Calificador IS
Calificador de repositorio
Para buscar dentro de un repositorio, usa el calificador repo:. Debes proporcionar el nombre completo del repositorio, incluido el propietario. Por ejemplo:

repo:github-linguist/linguist
Para buscar en un conjunto de repositorios, puedes combinar varios calificadores repo: con el operador booleano OR. Por ejemplo:

repo:github-linguist/linguist OR repo:tree-sitter/tree-sitter
Note

Tìm kiếm mã hiện không hỗ trợ biểu thức chính quy hoặc khớp một phần cho tên kho lưu trữ, do đó bạn sẽ cần nhập toàn bộ tên kho lưu trữ (bao gồm cả tiền tố người dùng) để trình định danh repo:hoạt động.

Tiêu chuẩn tổ chức và người dùng
Để tìm kiếm tệp trong một tổ chức, hãy sử dụng ký tự hạn định org:. Ví dụ:

org:github
Để tìm kiếm tệp trong tài khoản cá nhân, hãy sử dụng ký tự user:. Ví dụ:

user:octocat
Ghi chú

Tìm kiếm mã hiện không hỗ trợ biểu thức chính quy hoặc kết quả khớp một phần cho tên tổ chức hoặc tên người dùng, do đó bạn sẽ cần nhập toàn bộ tên tổ chức hoặc tên người dùng để trình hạn định hoạt động.

Trình độ ngôn ngữ
Để thu hẹp phạm vi tìm kiếm xuống một ngôn ngữ cụ thể, hãy sử dụng từ hạn định language:. Ví dụ:

language:ruby OR language:cpp OR language:csharp
Để biết danh sách đầy đủ các tên ngôn ngữ được hỗ trợ, hãy xem languages.yaml trong github-linguist/linguist . Nếu ngôn ngữ bạn muốn sử dụng không có trong danh sách, bạn có thể mở yêu cầu kéo để thêm ngôn ngữ đó.

Trình định tính đường dẫn
Để tìm kiếm trong đường dẫn tệp, hãy sử dụng ký tự hạn định path:. Điều này sẽ khớp với các tệp có chứa thuật ngữ ở bất kỳ đâu trong đường dẫn tệp. Ví dụ, để tìm kiếm các tệp có chứa thuật ngữ này unit_teststrong đường dẫn của chúng, hãy sử dụng:

path:unit_tests
Truy vấn trên sẽ khớp với cả src/unit_tests/my_test.pyvà src/docs/unit_tests.md, vì cả hai đều chứa unit_testmột vị trí nào đó trong đường dẫn của chúng.

Để chỉ khớp với tên tệp cụ thể (và không phải một phần của đường dẫn), bạn có thể sử dụng biểu thức chính quy:

path:/(^|\/)README\.md$/
Lưu ý rằng .tên tệp được thoát vì .nó có ý nghĩa đặc biệt đối với biểu thức chính quy. Để biết thêm thông tin về cách sử dụng biểu thức chính quy, hãy xem Sử dụng biểu thức chính quy .


Bạn cũng có thể sử dụng một số biểu thức toàn cục hạn chế trong định tính path:.

Ví dụ, để tìm kiếm các tệp có phần mở rộng txt, bạn có thể sử dụng:

path:*.txt

Để tìm kiếm các tệp JavaScript trong thư mục `src`, bạn có thể sử dụng:
path:src/*.js
Theo mặc định, biểu thức toàn cục không được neo vào điểm bắt đầu của đường dẫn, do đó biểu thức trên vẫn sẽ khớp với đường dẫn như app/src/main.js. Nhưng nếu bạn thêm tiền tố vào biểu thức /, thì nó sẽ bị phân cách ở đầu. Ví dụ:

path:/src/*.js
Lưu ý rằng *nó không khớp với ký tự /, do đó đối với ví dụ trên, tất cả kết quả sẽ là hậu duệ trực tiếp của thư mục src. Để tìm kiếm các kết quả khớp trong các thư mục con, sao cho kết quả bao gồm các tệp lồng nhau sâu như /src/app/testing/utils/example.js, bạn có thể sử dụng **. Ví dụ:

path:/src/**/*.js

Bạn cũng có thể sử dụng ký tự toàn cục ?. Ví dụ, để khớp với đường dẫn file.aachoặc file.abc, bạn có thể sử dụng:

path:*.a?c

Để tìm kiếm tên tệp có chứa ký tự đặc biệt như `*` hoặc `?`, chỉ cần sử dụng chuỗi dấu ngoặc kép:
path:"file?"
Biểu thức toàn cục bị vô hiệu hóa đối với các chuỗi được trích dẫn, do đó truy vấn trên sẽ chỉ khớp với các đường dẫn có chứa chuỗi ký tự file?.

Biểu tượng định tính
Bạn có thể tìm kiếm định nghĩa ký hiệu trong mã, chẳng hạn như định nghĩa hàm hoặc lớp, bằng cách sử dụng trình định danh symbol:. Tìm kiếm ký hiệu dựa vào phân tích mã bằng hệ sinh thái trình phân tích cây nguồn mở , do đó không cần cấu hình bổ sung hoặc tích hợp công cụ xây dựng.

Ví dụ, để tìm kiếm một ký hiệu có tên WithContext:

language:go symbol:WithContext
Ở một số ngôn ngữ, bạn có thể tìm kiếm ký hiệu bằng cách sử dụng tiền tố (ví dụ: tiền tố cho tên lớp của ký hiệu). Ví dụ, đối với một phương thức deleteRowstrong struct Maint, bạn có thể tra cứu xem symbol:Maint.deleteRowsphương thức đó sử dụng Go hay symbol:Maint::deleteRowsRust.

Bạn cũng có thể sử dụng biểu thức chính quy với ký hiệu hạn định. Ví dụ, truy vấn sau sẽ tìm các chuyển đổi mà mọi người đã triển khai trong Rust cho kiểu String:

language:rust symbol:/^String::to_.*/
Lưu ý rằng trình định danh này chỉ tìm kiếm định nghĩa chứ không phải tham chiếu và chưa hỗ trợ đầy đủ tất cả các loại ký hiệu hoặc ngôn ngữ. Trích xuất ký hiệu được hỗ trợ trong các ngôn ngữ sau.

Đập
C
C#
C++
Mã số
Thuốc tiên
Đi
X
Java
JavaScript
Mặt trăng
PHP
Bộ đệm giao thức
Trăn
R
Hồng ngọc
rỉ sét
thang độ
chim sơn ca
Nhanh
Bản đánh máy
Chúng tôi đang nỗ lực để hỗ trợ thêm nhiều ngôn ngữ hơn. Nếu bạn muốn đóng góp vào nỗ lực này, bạn có thể thêm hỗ trợ cho ngôn ngữ của mình vào hệ sinh thái trình phân tích cây nguồn mở mà Symbol Search dựa trên.

Tiêu chuẩn nội dung
Theo mặc định, các thuật ngữ không có hệ thống sẽ tìm kiếm đường dẫn tệp và nội dung. Để giới hạn tìm kiếm theo đúng nội dung của tệp chứ không phải đường dẫn tệp, hãy sử dụng trình hạn định content:. Ví dụ:

content:README.md
Truy vấn này chỉ khớp với các tệp có chứa thuật ngữ README.md, thay vì khớp với các tệp có tên README.md.

Vòng loại IS
Để lọc dựa trên thuộc tính kho lưu trữ, bạn có thể sử dụng trình hạn định is:. is:hỗ trợ các giá trị sau:

archived: Giới hạn tìm kiếm trong các kho lưu trữ đã lưu trữ.
fork: Giới hạn tìm kiếm trong các kho lưu trữ phân nhánh.
vendored: Giới hạn tìm kiếm đối với nội dung được phát hiện là đã được chuyển giao cho nhà cung cấp.
generated: Giới hạn tìm kiếm đối với nội dung được phát hiện là đã tạo.
Ví dụ:

path:/^MIT.txt$/ is:archived
Ten en cuenta que el calificador is: se puede invertir con el operador NOT. Para buscar repositorios no archivados, puedes buscar:

log4j NOT is:archived
Para excluir bifurcaciones de los resultados, puedes buscar:

log4j NOT is:fork
Uso de expresiones regulares
La búsqueda de código admite expresiones regulares para buscar patrones en el código. Puedes usar expresiones regulares en términos de búsqueda sin sistema operativo, así como en muchos calificadores, rodeando la expresión regular con barras diagonales.

Por ejemplo, para buscar la expresión regular sparse.*index, usarías:

/sparse.*index/
Ten en cuenta que tendrá que escapar las barras diagonales dentro de la expresión regular. Por ejemplo, para buscar archivos dentro del directorio App/src, usarías:

/^App\/src\//
Dentro de una expresión regular, \n significa un carácter de nueva línea, \t significa una pestaña y \x{hhhh} se puede usar para escapar cualquier carácter Unicode. Esto significa que puede usar expresiones regulares para buscar cadenas exactas que contengan caracteres que no se pueden escribir en la barra de búsqueda.

Las características de expresiones regulares más comunes funcionan en la búsqueda de código. Sin embargo, no se admiten las aserciones de “búsqueda en torno”.

Separación de términos de búsqueda
Todas las partes de una búsqueda, como los términos de búsqueda, las cadenas exactas, las expresiones regulares, los calificadores, los paréntesis y las palabras clave booleanas AND, OR y NOT, deben estar separados entre sí con espacios. La única excepción es que los elementos entre paréntesis, ( ), no necesitan estar separados de los paréntesis.

Si la búsqueda contiene varios componentes que no están separados por espacios u otro texto que no siga las reglas enumeradas anteriormente, la búsqueda de código intentará adivinar lo que quiere decir. A menudo se revierte al tratar ese componente de la consulta como texto exacto que se va a buscar. Por ejemplo, la consulta siguiente:

printf("hello world\n");
La búsqueda de código dejará de interpretar los paréntesis y comillas como caracteres especiales y, en su lugar, buscará archivos que contengan ese código exacto.

Si la búsqueda de código supone un error, siempre puedes obtener la búsqueda que querías usando comillas y espacios para aclarar el significado.

Distinción entre mayúsculas y minúsculas
De forma predeterminada, la búsqueda de código no distingue mayúsculas de minúsculas y en los resultados se incluyen ambas formas. Puedes realizar búsquedas con distinción entre mayúsculas y minúsculas mediante una expresión regular con la opción de no distinguir entre ambas desactivada. Por ejemplo, para buscar la cadena "True" se usaría:

/(?-i)True/
Ayuda y soporte técnico
¿Encontró lo que necesitaba?

Directiva de privacidad
¿Aún necesita ayuda?
Pregúntele a la comunidad de GitHub
Póngase en contacto con el soporte técnico.
Información legal
Một số nội dung này có thể đã được dịch tự động hoặc bằng AI.

© 2025 GitHub, Inc.
Điều khoản
Sự riêng tư
Tình trạng
Giá cả
Dịch vụ chuyên gia
Blog
Tổng quan về cú pháp tìm kiếm mã GitHub - Tài liệu GitHubhuant<!--
  <<< Author notes: Header of the course >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.![1000000926](https://github.com/user-attachments/assets/91815213-9a87-497e-beef-e43f80c50dda)
![1000000926](https://github.com/user-attachments/assets/923289be-45cd-42a2-b801-c0adb2cd6f39)

  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses Creative Commons Attribution 4.0 International.
-->

# GitHub Pages

_Create a site or blog from your GitHub repositories with GitHub Pages._

<!--
  <<< Author notes: Start of the course >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
  Each step should be wrapped in <details>/<summary>, with an `id` set.
  The start <details> should have `open` as well.
  Do not use quotes on the <details> tag attributes.
-->

<details id=0 open>
<summary><h2>Welcome</h2></summary>

With GitHub Pages, you can host project blogs, documentation, resumes, portfolios, or any other static content you'd like. Your GitHub repository can easily become its own website. In this course, we'll show you how to set up your own site or blog using GitHub Pages.

- **Who is this for**: Beginners, students, project maintainers, small businesses.
- **What you'll learn**: How to build a GitHub Pages site.
- **What you'll build**: We'll build a simple GitHub Pages site with a blog. We'll use [Jekyll](https://jekyllrb.com), a static site generator.
- **Prerequisites**: If you need to learn about branches, commits, and pull requests, take [Introduction to GitHub](https://github.com/skills/introduction-to-github) first.
- **How long**: This course is five steps long and takes less than one hour to complete.
  
**Course tips:**
  - Glossary terms will be _emphasised_ and linked to their definiton.

## How to start this course

1. Right-click **Start course** and open the link in a new tab.
   <br />[![start-course](https://user-images.githubusercontent.com/1221423/218596841-0645fe1a-4aaf-4f51-9ab3-8aa2d3fdd487.svg)](https://github.com/skills/github-pages/generate)
2. In the new tab, follow the prompts to create a new repository.
   - For owner, choose your personal account or an organization to host the repository.
   - We recommend creating a public repository—private repositories will [use Actions minutes](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions).
   - Name the repository something easy for you to recognize and remember.
   ![Screenshot of the "Create a new repository" page. The "Public" repository option is highlighted with an orange box.](/images/create-a-repository.png)
3. After your new repository is created, wait about 20 seconds, then refresh the page. Follow the step-by-step instructions in the new repository's README. [GitHub Actions](https://docs.github.com/en/actions) will automatically close this welcome and open the first step.

</details>

<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

<details id=1>
<summary><h2>Step 1: Enable GitHub Pages</h2></summary>

_Welcome to GitHub Pages and Jekyll :tada:!_

The first step is to enable GitHub Pages on this [repository](https://docs.github.com/en/get-started/quickstart/github-glossary#repository). When you enable GitHub Pages on a repository, GitHub takes the content that's on the main branch and publishes a website based on its contents.

### :keyboard: Activity: Enable GitHub Pages

1. Open a new browser tab, and work on the steps in your second tab while you read the instructions in this tab.
1. Under your repository name, click **Settings**.
1. Click **Pages** in the **Code and automation** section.
1. Ensure "Deploy from a branch" is selected from the **Source** drop-down menu, and then select `main` from the **Branch** drop-down menu.
1. Click the **Save** button.
1. Wait about _one minute_, then refresh this page for the next step.
   > Turning on GitHub Pages creates a deployment of your repository. GitHub Actions may take up to a minute to respond while waiting for the deployment. Future steps will be about 20 seconds; this step is slower.
   > **Note**: In the **Pages** of **Settings**, the **Visit site** button will appear at the top. Click the button to see your GitHub Pages site.

</details>

<!--
  <<< Author notes: Step 2 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
  Historic note: previous version checked for empty pull request, changed to the correct theme `minima`.
-->

<details id=2>
<summary><h2>Step 2: Configure your site</h2></summary>

_You turned on GitHub Pages! :tada:_

We'll work in a branch, `my-pages`, that I created for you to get this site looking great. :sparkle:

Jekyll uses a file titled `_config.yml` to store settings for your site, your theme, and reusable content like your site title and GitHub handle. You can check out the `_config.yml` file on the **Code** tab of your repository.

We need to use a blog-ready theme. For this activity, we will use a theme named "minima".

### :keyboard: Activity: Configure your site

1. Browse to the `_config.yml` file in the `my-pages` branch.
1. In the upper right corner, open the file editor.
1. Add a `theme:` set to **minima** so it shows in the `_config.yml` file as below:
    ```yml
    theme: minima
    ```
1. (optional) You can modify the other configuration variables such as `title:`, `author:`, and `description:` to further customize your site.
1. Commit your changes.
1. (optional) Create a pull request to view all the changes you'll make throughout this course. Click the **Pull Requests** tab, click **New pull request**, set `base: main` and `compare:my-pages`.
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Step 3 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
  Historic note: previous version checked the homepage content was not empty.
-->

<details id=3>
<summary><h2>Step 3: Customize your homepage</h2></summary>

_Nice work setting the theme! :sparkles:_

You can customize your homepage by adding content to either an `index.md` file or the `README.md` file. GitHub Pages first looks for an `index.md` file. Your repository has an `index.md` file so we can update it to include your personalized content.

### :keyboard: Activity: Create your homepage

1. Browse to the `index.md` file in the `my-pages` branch.
1. In the upper right corner, open the file editor.
1. Type the content you want on your homepage. You can use Markdown formatting on this page.
1. (optional) You can also modify `title:` or just ignore it for now. We'll discuss it in the next step.
1. Commit your changes to the `my-pages` branch.
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Step 4 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
  Historic note: previous version checked the file path. Previous version checked the front matter formatting.
-->

<details id=4>
<summary><h2>Step 4: Create a blog post</h2></summary>

_Your home page is looking great! :cowboy_hat_face:_

GitHub Pages uses Jekyll. In Jekyll, we can create a blog by using specially named files and frontmatter. The files must be named `_posts/YYYY-MM-DD-title.md`. You must also include `title` and `date` in your frontmatter.

**What is _frontmatter_?**: The syntax Jekyll files use is called YAML frontmatter. It goes at the top of your file and looks something like this:

```yml
---
title: "Welcome to my blog"
date: 2019-01-20
---
```

For more information about configuring front matter, see the [Jekyll frontmatter documentation](https://jekyllrb.com/docs/frontmatter/).

### :keyboard: Activity: Create a blog post

1. Browse to the `my-pages` branch.
1. Click the `Add file` dropdown menu and then on `Create new file`.
1. Name the file `_posts/YYYY-MM-DD-title.md`.
1. Replace the `YYYY-MM-DD` with today's date, and change the `title` of your first blog post if you'd like.
   > If you do edit the title, make sure there are hyphens between your words.
   > If your blog post date doesn't follow the correct date convention, you'll receive an error and your site won't build. For more information, see "[Page build failed: Invalid post date](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/troubleshooting-jekyll-build-errors-for-github-pages-sites)".
1. Type the following content at the top of your blog post:
   ```yaml
   ---
   title: "YOUR-TITLE"
   date: YYYY-MM-DD
   ---
   ```
1. Replace `YOUR-TITLE` with the title for your blog post.
1. Replace `YYYY-MM-DD` with today's date.
1. Type a quick draft of your blog post. Remember, you can always edit it later.
1. Commit your changes to your branch.
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Step 5 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

<details id=5>
<summary><h2>Step 5: Merge your pull request</h2></summary>

_Nice work, friend :heart:! People will be reading your blog in no time!_

You can now [merge](https://docs.github.com/en/get-started/quickstart/github-glossary#merge) your pull request!

### :keyboard: Activity: Merge your changes

1. Merge your changes from `my-pages` into `main`. If you created the pull request in step 2, just open that PR and click on **Merge pull request**. If you did not create the pull request earlier, you can do it now by following the instructions in step 2.
1. (optional) Delete the branch `my-pages`.
1. Wait about 20 seconds then refresh this page for the next step.

</details>

<!--
  <<< Author notes: Finish >>>
  Review what we learned, ask for feedback, provide next steps.
-->

<details id=X>
<summary><h2>Finish</h2></summary>

_Congratulations friend, you've completed this course!_

<img src=https://octodex.github.com/images/constructocat2.jpg alt=celebrate width=300 align=right>

Your blog is now live and has been deployed!

Here's a recap of all the tasks you've accomplished in your repository:

- You enabled GitHub Pages.
- You selected a theme using the config file.
- You learned about proper directory format and file naming conventions in Jekyll.
- You created your first a blog post with Jekyll!

### What's next?

- Keep working on your GitHub Pages site... we love seeing what you come up with!
- We'd love to hear what you thought of this course [in our discussion board](https://github.com/skills/.github/discussions).
- [Take another GitHub Skills course](https://github.com/skills).
- [Read the GitHub Getting Started docs](https://docs.github.com/en/get-started).
- To find projects to contribute to, check out [GitHub Explore](https://github.com/explore).

</details>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/skills/.github/discussions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2022 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)
