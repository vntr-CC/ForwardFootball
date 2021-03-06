# Opciones de Biblioteca de Aserciones 馃摀

Las diferentes opciones contempladas haciendo uso del lenguaje de programaci贸n Julia son las siguientes:

## Test.jl

El m贸dulo [**Test**](https://docs.julialang.org/en/v1/stdlib/Test/) proporciona una funcionalidad de prueba unitaria simple. La prueba unitaria es una forma de ver si el c贸digo es correcto al verificar que los resultados son los esperados. Es de gran utilidad para asegurarse de que el c贸digo sigue funcionando despu茅s de realizar cambios y que puede usarse durante el desarrollo, como si fuera una forma de especificar los comportamientos que debe tener el c贸digo cuando est茅 completo.

La nomenclatura habitual viene definida en este ejemplo:

```julia
@testset "trigonometric identities" begin
           胃 = 2/3*蟺
           @test sin(-胃) 鈮? -sin(胃)
end
```

Al proporcionar una funcionalidad simple, en adici贸n haremos uso de la librer铆a [**SafeTestsets.jl**](https://github.com/YingboMa/SafeTestsets.jl) para encapsular los `@testset` en un m贸dulo, impidiendo as铆 que los diferentes sets compartan variables que puedan causar errores.

## XUnit.jl
Visto el caracter simplista de la anterior librer铆a, **XUnit.jl** pretende ser un reemplazo directo para las macros definidas por **Test.jl**. Esto quiere decir que la sintaxis es muy similar, pero da soporte a una serie de funcionalidades adicionales de las que podemos obtener m谩s informaci贸n [en su reporsitorio](https://github.com/RelationalAI-oss/XUnit.jl).
