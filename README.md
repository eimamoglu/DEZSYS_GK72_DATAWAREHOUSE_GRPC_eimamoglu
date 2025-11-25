# Middleware Engineering "DEZSYS_GK_HELLOWORLD_GRPC"
Verfasser: Elyesa Imamoglu, 4CHIT

## Fragen und Antworten

1. What is gRPC and why does it work accross languages and platforms?

   gRPC ist ein leistungsfähiges RPC-Framework, das Dienste über Netzwerke verbindet.
   Es funktioniert sprach- und plattformübergreifend, weil es:
   Protocol Buffers zur Schnittstellenbeschreibung nutzt
   für viele Sprachen automatisch Client- und Server-Code generiert
   auf HTTP/2 basiert (effizient, schnell)
2. Describe the RPC life cycle starting with the RPC client?

   Client ruft die Stub-Methode auf
   Anfrage wird in Protobuf serialisiert
   Über HTTP/2 an Server gesendet
   Server deserialisiert die Daten
   Server führt Methode aus
   Antwort wird serialisiert
   Server sendet Antwort zurück
   Client deserialisiert und liefert Ergebnis zurück
3. Describe the workflow of Protocol Buffers?

   .proto-Datei definieren
   Mit protoc Code generieren
   Daten werden serialisiert/deserialisiert
   Im Programm wie normale Objekte verwenden
4. What are the benefits of using protocol buffers?

   Sehr schnell & kompakt
   Stark typisiert
   Kompatibel bei Versionierung
   Automatische Codegenerierung
   Plattform- und sprachunabhängig
5. When is the use of protocol not recommended?

   Wenn Daten menschlich lesbar sein müssen
   Für Browser-APIs, die lieber JSON nutzen
   Für häufiges Debugging per Textformat
   Bei sehr dynamischen, unstrukturierten Daten
6. List 3 different data types that can be used with protocol buffers?

   int32
   string
   bool
   (Bzw. auch: bytes, float, enum, usw.)
## Implementierung und Anleitung für die nötigen Schritte (GK)

Start HelloWorldServer (Java)  
`gradle clean build`  
`gradle runServer`

Start HelloWorldClient (Java)  
`gradle runClient`
  

-------------------------------- Python 

Add grpcio packages  
`pip3 install grpcio grpcio-tools`  

Compile .proto file  
`python3 -m grpc_tools.protoc -I src/main/proto  
  --python_out=src/main/resources  
  --grpc_python_out=src/main/resources  
  src/main/proto/hello.proto`  

Start HelloWorldClient (Python)  
`python3 src/main/resources/helloWorldClient.py`  

## Quellen

[1] „gRPC“, gRPC. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://grpc.io/

[2] „gRPC-Spring-Boot-Starter Documentation“, grpc-spring-boot-starter. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://yidongnan.github.io/grpc-spring-boot-starter/en/

[3] J. Holiday, „Implement gRPC Service Using Java + Gradle“, Medium. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://intuting.medium.com/implement-grpc-service-using-java-gradle-7a54258b60b8

[4] „Introduction about gRPC and implement with Spring boot“, SHIFT ASIA | Dev Blog. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://shiftasia.com/community/introduction-grpc-and-implement-with-spring-boot/

[5] „Introduction to gRPC“, gRPC. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://grpc.io/docs/what-is-grpc/introduction/

[6] „Introduction to gRPC | Baeldung“. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://www.baeldung.com/grpc-introduction

[7] „Quick start“, gRPC. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://grpc.io/docs/languages/java/quickstart/

[8] „What is gRPC?“, gRPC. Zugegriffen: 25. November 2025. [Online]. Verfügbar unter: https://grpc.io/docs/what-is-grpc/
