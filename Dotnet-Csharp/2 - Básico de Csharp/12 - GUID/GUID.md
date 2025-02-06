#csharp
Global Unique Identifier é um identificador único de 128 bits usado para identificar informações em sistemas de computador.
Amplamente utilizado para garantir que cada valor gerado seja único em um contexto global.
Útil para banco de dados, interfaces de programação de aplicativos (APIs) e sistemas distribuídos.

Identifica um objeto usando um valor de 128 bits (32 characteres) com hifens.
Exemplo: __123e4567-e89b-12d3-a456-426614174000__

## Como criar um GUID
---
usamos o pacote __System__ que é um namespace essencial que contém classes e tipos fundamentais para a programação na plataforma .NET. Ele oferece uma ampla gama de funcionalidades básicas que são usados em praticamente todos os programas no C#.

System possui a classe __guid__ que nos auxilia na criação desse identificador único.

```csharp
using System;

namespace StudyGuid
{
	class GuidExample
	{
		public Guid CreateGuid()
		{
			Guid newGuid = Guid.NewGuid();
			// ou var newGuid
			return newGuid;
		}
	}
}
```

Toda vez que é chamado _CreateGuid()_ ele gera um valor novo seguindo as regras definidas pelo GUI, sendo um identificador único (ID) extremamente útil no desenvolvimento.