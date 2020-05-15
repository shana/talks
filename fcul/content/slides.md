<!-- .slide: data-background="#009fb1" -->
# Compiladores na Unity

>>>
# Compiladores, *transpiladores*?

>>>
### clang <!-- .element: class="fragment fade-in pos1 color5" -->
### .NET/Mono <!-- .element: class="fragment fade-in pos2 color2" -->
### Shaders <!-- .element: class="fragment fade-in pos3 color7" -->
# **Quantos** compiladores são *precisos*?
### shaderlab <!-- .element: class="fragment fade-in pos1 color3" -->
### il2cpp <!-- .element: class="fragment fade-in pos4 color4" -->
### Emscripten <!-- .element: class="fragment fade-in pos5 color1" -->
### Burst <!-- .element: class="fragment fade-in pos6 color6" -->

>>>
# Os **compiladores**

>>>
><!-- .element: class="bgblue" -->
># Engine
>Clang - C++<!-- .element: class="fragment fade-in" -->

vvv
# *GCC* vs **Clang**

vvv
# Tempos de **Compilação**

vvv
# Avisos, quais avisos?

>>>

><!-- .element: class="bgorange" -->
># Gráficos
>Shaders - MSL, GLSL, HLSL, SPIR-V, OpenGL, PSL, Cg...<!-- .element: class="fragment fade-in" -->  
>Shaderlab<!-- .element: class="fragment fade-in" -->

vvv
# Quando C não é **C**

<pre class="long fragment fade-in"><code class="hljs language-c" data-line-numbers="2|4,2-4">
#define MINIMUM_FLOAT_VALUE -340282346638528859811704183484516925440.

if (offsets.z > -MINIMUM_FLOAT_VALUE) {
	...	
}
</code></pre>

>>>
<!-- .slide: class="bgblue" -->
># Lógica do jogo
>.NET - C#<!-- .element: class="fragment fade-in" -->  
>Burst - C#<!-- .element: class="fragment fade-in" -->

vvv
# **Burst** e *DOD*

vvv
![](content/dots.gif)<!-- .element: width="75%"-->

vvv
![](content/oo_design.png)<!-- .element: width="50%"-->

vvv
![](content/do_design.png)<!-- .element: width="40%"-->

vvv
<pre class="long"><code data-trim class="hljs language-csharp">
[BurstCompile]
private struct CopyJob : IJob
{
    [ReadOnly]
    public NativeArray&lt;float&gt; Input;

    [WriteOnly]
    public NativeArray&lt;float&gt; Output;

    public void Execute()
    {
        for (int i = 0; i < Input.Length; i++)
        {
            Output[i] = Input[i];
        }
    }
}
</code></pre>

vvv
# Sem vectorização
![](content/burst-noalias.png)<!-- .element: width="100%"-->  

vvv
# Com vectorização
![](content/burst-noalias-vectorized.png)<!-- .element: width="100%"-->  

vvv
### **32 floats** copiados por iteração do loop
<pre class="long"><code data-trim class="hljs language-armasm">
vmovups ymm0, ymmword ptr [rcx - 96]
vmovups ymm1, ymmword ptr [rcx - 64]
vmovups ymm2, ymmword ptr [rcx - 32]
vmovups ymm3, ymmword ptr [rcx]
vmovups ymmword ptr [rdx - 96], ymm0
vmovups ymmword ptr [rdx - 64], ymm1
vmovups ymmword ptr [rdx - 32], ymm2
vmovups ymmword ptr [rdx], ymm3
</code></pre>

>>>
<!-- .slide: class="bgorange" -->
># Plataformas
>il2cpp - IL<!-- .element: class="fragment fade-in" -->  
>Emscripten - C++<!-- .element: class="fragment fade-in" -->

vvv
# **IL2CPP**, because why not!

vvv
><!-- .element: class="bgblue" -->
><h1>C#</h1>

><!-- .element: class="bgorange fragment fade-in" -->
># IL

><!-- .element: class="bgblue fragment fade-in" -->
># C++!

vvv
# Emscripten

vvv
><!-- .element: class="bgorange" -->
># C++

><!-- .element: class="bgblue fragment fade-in" -->
># Web!

>>>
<!-- .slide: data-background-image="content/allthethings.jpg" data-background-size="880px" -->
