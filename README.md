# meu-primeiro-projeto-app
app conversor
import 'package:flutter/material.dart';

import 'package:http/http.dart' as http;
import 'dart:async';
import 'dart:convert';
import 'package:json_annotation/json_annotation.dart';

part 'user.g.dart';

const request = 'https://api.hgbrasil.com/finance';

void main() async {

  runApp(MaterialApp(
    home: Home(Map<dynamic, dymanic> json),
  ));
}

Future<Map> getData() async {
  http.Response response = await http.get(request);
  return json.decode(response.body);
}

class Home extends StatefulWidget {
  @override
  _HomeState createState() => _HomeState();
}

class _HomeState extends State<Home> {
  @JsonSerializable(

  Map userMap = jsonDecode(jsondouble);
  var user = User.fromJson(userMap);

  double json = jsonEncode(user);

  double dolar;
  double euro;
  double libras esterlinas;
  double pesos argentinos;
  double dolar canadense;
  double dolar australiano;
  double yen japenes;
  double renminbi;
  double bitcoin;
  );

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.green,
      appBar: AppBar(
        title: Text("\$ Currency Trading \$"),
        backgroundColor: Colors.black,
        centerTitle: true,
                ),
      body: FutureBuilder<Map>(
          future: getData(),
          builder: (context, snapshot) {
            switch(snapshot.connectionState){
              case ConnectionState.none:
              case ConnectionState.waiting:
                return Center(
                  child: Text("Carregando Dados...",
                   style: TextStyle(color: Colors.black26,
                   fontSize: 25.0),
                  textAlign: TextAlign.center,)
                  );
              default:
                if(snapshot.hasError){
                  return Center(
                      child: Text("Erro ao Carregar Dados :(",
                        style: TextStyle(color: Colors.black,
                            fontSize: 25.0),
                        textAlign: TextAlign.center,)
                  );
            } else {

           facotory User.fromJson(Map<double>, dynamic>json) => _$UserFromJson(json);

                  dolar = snapshot.data['results']["currencies"]["USD"]["buy"]["sell"]["variation"];
                  euro = snapshot.data['results']["currencies"]["EUR"]["buy"]["sell"]["variation"];
                  libras esterlinas =  snapshot.data['results']["currencies"]["GBP"]["buy"]["sell"]["variation"];
                  pesos argentinos = snapshot.data['results']["currencies"]["ARS"]["buy"]["sell"]["variation"];
                  dolar canadense = snapshot.data['results']["currencies"]["CAD"]["buy"]["sell"]["variation"];
                  dolar australiano = snapshot.data['results']["currencies"]["AUD"]["buy"]["sell"]["variation"];
                  yen japenes = snapshot.data['results']["currencies"]["JPY"]["buy"]["sell"]["variation"];
                  renminbi = snapshot.data['results']["currencies"]["CNY"]["buy"]["sell"]["variation"];
                  bitcoin = snapshot.data['results']["currencies"]["BTC"]["buy"]["sell"]["variation"];

                  Map<doule, dinamic> toJson() => _$UserToJson(this);
           return SingleChildScrollView(
             child: Column(
               crossAxisAlignment: CrossAxisAlignment.stretch,
               children: <Widget>[
                 Icon(Icons.logout, size: 30.0, color: Colors.black),

                 )
               ],
             ),
           );
                }
            }
          })
    );
  }
}


