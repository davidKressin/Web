---
title: "Principios SOLID"
description: "Un repaso por estos criterios de desarrollo de software."
pubDate: "Sep 21 2023"
heroImage: "/Web/solid.png"
---

<body>
    <article id="ff192bb4-e235-4532-99e5-dc7e901ff515" class="page sans">
        <header>
            <strong>Índice:</strong>
            <nav id="1ee078d1-5156-4681-b1d5-af63f2b3682e" class="block-color-gray table_of_contents">
            <div class="table_of_contents-item table_of_contents-indent-0">
                <a class="table_of_contents-link" href="#0c455ca6-dcb6-495c-81f2-cb60b02566bf">¿Cuáles son los principios SOLID?</a>
            </div>
            <div class="table_of_contents-item table_of_contents-indent-0">
                <a class="table_of_contents-link" href="#cd1f5094-5667-420e-bf8b-8e51f2913b15">Casos de aplicación:</a>
            </div>
            </nav>
            <p id="2a151e76-47d8-4d5d-b01f-e86452b46b95" class=""></p>
            <p id="33c0c6e9-c932-4ba5-8f9a-36104c0c2305" class="">Los principios SOLID son un conjunto de cinco principios de diseño de software que promueven la creación de <strong>código limpio</strong>, <strong>mantenible </strong>y <strong>escalable</strong>. Estos principios fueron presentados por Robert C. Martin (también conocido como &quot;<strong>Tío Bob</strong>&quot;) en la década del 2000 como una guía para escribir software orientado a objetos de alta calidad</p>
            <h2 id="0c455ca6-dcb6-495c-81f2-cb60b02566bf" class="">¿Cuáles son los principios SOLID?</h2>
            <ul id="472a024a-e2e2-4f20-8bce-15939e2438c8" class="bulleted-list"><li style="list-style-type:disc"><strong>S - Principio de Responsabilidad Única (Single Responsibility Principle, SRP):</strong> Este principio establece que una clase debe tener una única responsabilidad y no debe estar sobrecargada con múltiples tareas.</li></ul><ul id="2787d778-3c48-489f-bcf0-bd1936d27a44" class="bulleted-list"><li style="list-style-type:disc"><strong>O - Principio de Abierto/Cerrado (Open/Closed Principle, OCP):</strong> El principio OCP establece que las entidades de software (clases, módulos, etc.) deben estar abiertas para su extensión pero cerradas para su modificación. Esto significa que puedes agregar nuevas funcionalidades sin cambiar el código existente.</li></ul><ul id="9f08dd3c-44e6-4a0a-ab4c-c2216725a929" class="bulleted-list"><li style="list-style-type:disc"><strong>L - Principio de Sustitución de Liskov (Liskov Substitution Principle, LSP):</strong> Este principio se refiere a la capacidad de reemplazar una instancia de una clase base por una instancia de una clase derivada sin afectar la integridad del programa. En otras palabras, las clases derivadas deben ser substituibles por sus clases base sin causar problemas.</li></ul><ul id="c14ae418-daaa-4b57-a12d-f6130aa625d8" class="bulleted-list"><li style="list-style-type:disc"><strong>I - Principio de Segregación de Interfaces (Interface Segregation Principle, ISP):</strong> El principio ISP establece que una clase no debe ser forzada a implementar interfaces que no utiliza. En su lugar, una clase debe implementar interfaces específicas que se ajusten a sus necesidades.</li></ul><ul id="6ac1307d-1b04-417e-b8a5-197b0904d419" class="bulleted-list"><li style="list-style-type:disc"><strong>D - Principio de Inversión de Dependencia (Dependency Inversion Principle, DIP):</strong> El principio DIP dice que las clases de alto nivel no deben depender de las clases de bajo nivel, sino que ambas deben depender de abstracciones. Además, las abstracciones no deben depender de los detalles, sino que los detalles deben depender de las abstracciones.</li></ul><p id="5d5e2be1-90b9-49f6-8718-949df4971a9f" class="">
</p><h2 id="cd1f5094-5667-420e-bf8b-8e51f2913b15" class="">Casos de aplicación:</h2><p id="10de8038-f15f-4400-8130-df18127b87c7" class="">
</p><p id="b6bca2ee-ba8b-4d69-a1f2-830447c93c3e" class=""><strong>S - Principio de Responsabilidad Única (Single Responsibility Principle, SRP)</strong><div class="indented"><p id="622bec09-d67d-4761-82e5-48c55d5723d9" class="">Tomemos como ejemplo esta clase llama Email que se encarga de enviar un mensaje, entrar y salir de la cuenta.</p>
<pre id="5c5e55c5-3916-4fe3-9347-499f902d32fa" class="code">
<code>
class Email{
  sendEmail(){
    console.log(&quot;Enviando email&quot;)
  }
  login(){
    console.log(&quot;ingresando a la cuenta&quot;)
  }
  logout(){
    console.log(&quot;saliendo de la cuenta&quot;)
  }
}

const email = new Email();
email.login();
email.sendEmail();
email.logout();

// console
&quot;ingresando a la cuenta&quot;
&quot;Enviando email&quot;
&quot;saliendo de la cuenta&quot;</code></pre>
<p id="aba12a46-48e3-4071-bc32-198df85c981a" class="">No cumple con este principio ya que una Clase llamada Email debe ser independiente de la autenticación. Para solucionarlo crearemos otra clase “Authentication” que se encargue del login y logout.</p><pre id="0e464788-eb11-4b90-83e6-ec145ecafd03" class="code">
<code>
class Email{
    sendEmail(){
        console.log(&quot;Enviando email&quot;)
    }
}
class Authentication{
    login(){
        console.log(&quot;ingresando a la cuenta&quot;)
    }
    logout(){
        console.log(&quot;saliendo de la cuenta&quot;)
    }
}

const email = new Email();
const auth = new Authentication();

auth.login();
email.sendEmail();
auth.logout();</code></pre></div></p><p id="f7749f07-9f74-4656-8400-f290fa511fc9" class="">

</p><p id="2c2a1425-5f84-42a4-abf8-2fa05d3babf4" class=""><strong>O - Principio de Abierto/Cerrado (Open/Closed Principle, OCP)</strong><div class="indented"><p id="05d8cdea-a589-4d70-bb6c-408e17d22789" class="">
</p></div></p></div></article></body>


