# Manual Tecnico Alfonso Bonilla Aragón Airport
Desarrolladores 

Rui Yu Lei Wu       
Marco Antonio Riascos Salguero

## Introducción

Bienvenido al Manual tecnico del sistema del Aeropuerto Alfonso Bonilla Aragon; Este programa le permitirá conocer las principales operaciones y acciones de un aeropuerto; acciones que pueden ser realizadas por  el controlador aéreo del aeropuerto, una aerolínea y el usuario al que se le va a prestar el servicio; de manera clara, sencilla y eficiente. Tambien contiene las clases con las cuales se rige el programa, junto con  sus implemetaciones y relaciones de las subclases

## Contenido

1. Inicio Rápido
      1.1. Requisitos del Sistema
      1.2. Ejecución
2. Clases y subclases impementadas en el programa Airport
        2.1. Airport
        2.2 Aircraft
            2.2.1. Airplane 
            2.2.2. Jet
            2.2.3 Helicopter
        2.3. AircraftFactoty
        2.4. Airline
        2.5 AirTrafficControler
        2.6 Flight
        2.7 People
            2.7.1. Passenger
            2.7.2. Crewmate
        2.8. gate 

3. Funcionalidades
     3.1. Controlador Aéreo
         3.1.1. Asignación de puertas de embarque 
         3.1.2. Notificación de las aeronaves en el aire
         3.1.3. Despegue y aterrizaje de aeronaves
      3.2. Aerolínea
         3.2.1. Asignación de vuelos a aeronaves
      3.3. Usuario
         3.3.1. Reservar un vuelo 

4. Solución de Problemas Comunes
        4.1. No se puede abrir el programa
        4.2. Error en los cálculos

5. Diagrama UML

6. Contacto y Soporte Técnico


### 1. Inicio Rápido
 1.1. Requisitos del Sistema

- Sistema Operativo: Windows 10 o superior
- Procesador: 1 GHz o superior
- Memoria RAM: 512 MB
- Espacio en Disco: 10 MB


 1.2. Ejecución

Para ejecutar Aeropuerto.cpp, haga doble clic en el archivo principal del programa (main.cpp); para ejecutar desde la terminal; escriba todos los archivos .cpp que compone el programa; archivos tales como airport.cpp, airline.cpp, Passenger.cpp, crewmate.cpp, aircraft.cpp, airplane.cpp, jet.cpp, helicopter.cpp, airTrafficControler.cpp, people.cpp, main.cpp. Para ejecuciones desde un IDLE, se necesitó importar todos archivos cpp y archivos cabeceros .h, y utilizar la opción de corre o ejecutar con la que cuenta la interfase del IDLE

### 2. Clases y subclases impementadas en el programa Airport

##### 2.1 Airport
Clase `Airport`:

**Atributos:**
1. `string name`: Almacena el nombre del aeropuerto.

2. `vector<Flight*> flights`: Almacena un vector de punteros a objetos de la clase `Flight`, que representan los vuelos relacionados con el aeropuerto.

3. `vector<Aircraft*> aircrafts`: Almacena un vector de punteros a objetos de la clase `Aircraft`, que representan las aeronaves relacionadas con el aeropuerto.

4. `vector<Gate*> gates`: Almacena un vector de punteros a objetos de la clase `Gate`, que representan las puertas de embarque relacionadas con el aeropuerto.

5. `vector<Airline*> airlines`: Almacena un vector de punteros a objetos de la clase `Airline`, que representan las aerolíneas relacionadas con el aeropuerto.

6. `AirTrafficControler* atc`: Almacena un puntero a un objeto de la clase `AirTrafficControler`, que parece estar relacionado con el control del tráfico aéreo en el aeropuerto.

**Métodos:**
1. `Airport(string name)`: Constructor de la clase `Airport`, que se utiliza para crear una instancia de la clase y establecer el nombre del aeropuerto.

2. `string getName()`: Devuelve el nombre del aeropuerto.

3. `void setName(string name)`: Establece el nombre del aeropuerto.

4. `vector<Flight*> getFlights()`: Devuelve un vector de punteros a objetos `Flight`, que representan los vuelos relacionados con el aeropuerto.

5. `vector<Aircraft*> getAircrafts()`: Devuelve un vector de punteros a objetos `Aircraft`, que representan las aeronaves relacionadas con el aeropuerto.

6. `vector<Gate*> getGates()`: Devuelve un vector de punteros a objetos `Gate`, que representan las puertas de embarque relacionadas con el aeropuerto.

7. `vector<Airline*> getAirlines()`: Devuelve un vector de punteros a objetos `Airline`, que representan las aerolíneas relacionadas con el aeropuerto.

8. `AirTrafficControler* getAirTrafficControler()`: Devuelve un puntero al objeto `AirTrafficControler`, que parece estar relacionado con el control del tráfico aéreo en el aeropuerto.

9. `void createAircraft()`: Crea una aeronave y la agrega a las aeronaves relacionadas con el aeropuerto.

10. `void createAirline()`: Crea una aerolínea y la agrega a las aerolíneas relacionadas con el aeropuerto.

11. `void menu(vector<string> Destinations)`: Muestra un menú relacionado con el aeropuerto, posiblemente utilizando destinos como argumento.

12. `void addAircraft(Aircraft *aircraft)`: Agrega una aeronave al aeropuerto.

13. `void addFlight(Flight *flight)`: Agrega un vuelo al aeropuerto.

14. `void addAirline(Airline *airline)`: Agrega una aerolínea al aeropuerto.

15. `void setVecGates(vector<Gate*> gates)`: Establece el vector de puertas de embarque relacionadas con el aeropuerto.

16. `void setVecAircrafts(vector<Aircraft*> aircrafts)`: Establece el vector de aeronaves relacionadas con el aeropuerto.

17. `void setVecFlights(vector<Flight*> flights)`: Establece el vector de vuelos relacionados con el aeropuerto.

18. `void createGate()`: Crea una puerta de embarque y la agrega a las puertas de embarque relacionadas con el aeropuerto.

19. `void createAirTrafficControler()`: Crea un controlador de tráfico aéreo y lo relaciona con el aeropuerto.

Estos métodos y atributos permiten la gestión de información y operaciones relacionadas con un aeropuerto, como la creación de vuelos, aeronaves, aerolíneas, puertas de embarque y el control del tráfico aéreo.

##### 2.2. Aircraft
Clase `Aircraft`:

**Atributos:**
1. `map<int, int> mapLocation`: Un mapa que almacena la ubicación del avión, probablemente con coordenadas (latitud y longitud).

2. `string type_aircraft`: El tipo de aeronave (por ejemplo, "Boeing 747").

3. `string brand`: La marca de la aeronave (por ejemplo, "Boeing").

4. `int model`: El modelo de la aeronave.

5. `int capacity`: La capacidad de pasajeros de la aeronave.

6. `int maxium_speed`: La velocidad máxima de la aeronave.

7. `int Autonomy`: La autonomía (distancia máxima que puede recorrer) de la aeronave.

8. `int Year_of_manufacture`: El año de fabricación de la aeronave.

9. `int state`: El estado de la aeronave.

10. `vector<Flight> vec_flights`: Un vector de objetos `Flight` que representa los vuelos relacionados con la aeronave.

11. `int location`: La ubicación actual de la aeronave.

12. `int id`: El identificador único de la aeronave.

13. `bool flying`: Un indicador que representa si la aeronave está volando o no.

**Métodos:**
1. `Aircraft()`: Constructor por defecto de la clase `Aircraft`.

2. `Aircraft(const string& type_aircraft, const string& brand, int model, int capacity, int maxSpeed, int autonomy, int yearOfManufacture, int state, int location, int id, bool flying)`: Constructor parametrizado que inicializa los atributos de la aeronave al crear una instancia.

3. `string getBrand()`: Devuelve la marca de la aeronave.

4. `int getModel()`: Devuelve el modelo de la aeronave.

5. `int getCapacity()`: Devuelve la capacidad de pasajeros de la aeronave.

6. `int getMaxium_speed()`: Devuelve la velocidad máxima de la aeronave.

7. `int getAutonomy()`: Devuelve la autonomía de la aeronave.

8. `int getYear_of_manufacture()`: Devuelve el año de fabricación de la aeronave.

9. `int getState()`: Devuelve el estado de la aeronave.

10. `int getvec_flights()`: Devuelve el número de vuelos relacionados con la aeronave.

11. `int getMax_altitude()`: Devuelve la altitud máxima de la aeronave.

12. `int getNum_engines()`: Devuelve el número de motores de la aeronave.

13. `int getCategory()`: Devuelve la categoría de la aeronave.

14. `int getLocation()`: Devuelve la ubicación actual de la aeronave.

15. `bool getFull_assigned()`: Devuelve un indicador que representa si la aeronave está completamente asignada.

16. `int getId()`: Devuelve el identificador único de la aeronave.

17. `void setType(string type_aircraft)`: Establece el tipo de aeronave.

18. `void setBrand(string brand)`: Establece la marca de la aeronave.

19. `void setModel(int model)`: Establece el modelo de la aeronave.

20. `void setCapacity(int capacity)`: Establece la capacidad de pasajeros de la aeronave.

21. `void setMaxium_speed(int maxium_speed)`: Establece la velocidad máxima de la aeronave.

22. `void setAutonomy(int Autonomy)`: Establece la autonomía de la aeronave.

23. `void setYear_of_manufacture(int Year_of_manufacture)`: Establece el año de fabricación de la aeronave.

24. `void setState(int state)`: Establece el estado de la aeronave.

25. `void setMax_altitude(int max_altitude)`: Establece la altitud máxima de la aeronave.

26. `void setNum_engines(int num_engines)`: Establece el número de motores de la aeronave.

27. `void setCategory(int category)`: Establece la categoría de la aeronave.

28. `void setLocation(int location)`: Establece la ubicación actual de la aeronave.

29. `void setFull_assigned(string full_assigned)`: Establece si la aeronave está completamente asignada.

30. `void setId(int id)`: Establece el identificador único de la aeronave.

31. `void setDeparture_date(string departure_date)`: Establece la fecha de salida de la aeronave.

32. `void setArrival_date(string arrival_date)`: Establece la fecha de llegada de la aeronave.

33. `void addFlight(Flight flight)`: Agrega un vuelo al vector de vuelos relacionados con la aeronave.

34. `virtual void landing()`: Un método virtual que representa la acción de aterrizaje de la aeronave. Puede ser implementado de manera diferente en subclases.

35. `virtual void taking_off()`: Un método virtual que representa la acción de despegue de la aeronave. Puede

 ser implementado de manera diferente en subclases.

36. `void notify_location(int id, int altitude, bool flying)`: Notifica la ubicación actual de la aeronave y otros detalles relacionados con el control del tráfico aéreo.

37. `void update(map<int, int> mapLocation_atc)`: Actualiza la ubicación de la aeronave utilizando información del control de tráfico aéreo.

38. `bool getFlying()`: Devuelve un valor booleano que indica si la aeronave está volando.

39. `string getType_aircraft()`: Devuelve el tipo de aeronave.

40. `void setFlying(bool flying)`: Establece si la aeronave está volando o no.

41. `void addVec_flights(Flight flights)`: Agrega un vuelo al vector de vuelos relacionados con la aeronave.

42. `void printCommonDetails()`: Imprime detalles comunes de la aeronave.

43. `void printLocation()`: Imprime la ubicación actual de la aeronave.

44. `void printVec_flights()`: Imprime los vuelos relacionados con la aeronave.

45. `void updatePermission(bool permission)`: Actualiza el permiso o autorización de la aeronave (posiblemente relacionado con el control de tráfico aéreo).

##### 2.2.1. Airplane
Clase `Airplane` (Hereda de `Aircraft`):

**Atributos adicionales:**
1. `int max_altitude`: La altitud máxima que puede alcanzar el avión.

2. `int num_engines`: El número de motores del avión.

3. `int category`: La categoría del avión.

4. `int seats`: La cantidad total de asientos en el avión.

5. `int avalibleSeats`: La cantidad de asientos disponibles en el avión.

**Métodos adicionales:**
1. `Airplane()`: Constructor por defecto de la clase `Airplane`.

2. `Airplane(...)`: Constructor parametrizado que inicializa los atributos de la clase `Airplane` al crear una instancia. Este constructor también llama al constructor de la clase base `Aircraft` para inicializar sus atributos.

3. `~Airplane()`: Destructor de la clase `Airplane`.

4. `int getNum_engines()`: Devuelve el número de motores del avión.

5. `int getCategory()`: Devuelve la categoría del avión.

6. `int getMax_altitude()`: Devuelve la altitud máxima que puede alcanzar el avión.

7. `void setMax_altitude(int max_altitude)`: Establece la altitud máxima del avión.

8. `void setNum_engines(int num_engines)`: Establece el número de motores del avión.

9. `void setCategory(int category)`: Establece la categoría del avión.

10. `void setSeats(int seats)`: Establece la cantidad total de asientos en el avión.

11. `int getSeats()`: Devuelve la cantidad total de asientos en el avión.

12. `int getAvalibleSeats()`: Devuelve la cantidad de asientos disponibles en el avión.

13. `void setAvalibleSeats(int avalibleSeats)`: Establece la cantidad de asientos disponibles en el avión.

14. `void landing() override`: Implementación de la acción de aterrizaje específica para un avión. Este método anula el método virtual `landing` definido en la clase base `Aircraft`.

15. `void taking_off() override`: Implementación de la acción de despegue específica para un avión. Este método anula el método virtual `taking_off` definido en la clase base `Aircraft`.

La clase `Airplane` representa un tipo específico de aeronave (avión) que hereda los atributos y métodos de la clase base `Aircraft` y agrega atributos y comportamientos específicos relacionados con los aviones, como la altitud máxima, el número de motores, la categoría y la gestión de asientos.

##### 2.2.2. Jet
Clase `Jet` (Hereda de `Aircraft`):

**Atributos adicionales:**
1. `string owner`: El propietario o dueño de la aeronave.

2. `vector<string> services`: Un vector que almacena los servicios asociados a la aeronave.

3. `vector<string> destinies`: Un vector que almacena los destinos asociados a la aeronave.

**Métodos adicionales:**
1. `Jet(...)`: Constructor parametrizado que inicializa los atributos de la clase `Jet` al crear una instancia. Este constructor también llama al constructor de la clase base `Aircraft` para inicializar sus atributos.

2. `string getOwner()`: Devuelve el propietario o dueño de la aeronave.

3. `vector<string> getServices()`: Devuelve el vector de servicios asociados a la aeronave.

4. `vector<string> getDestinies()`: Devuelve el vector de destinos asociados a la aeronave.

5. `void setOwner(string owner)`: Establece el propietario o dueño de la aeronave.

6. `void addService(string service)`: Agrega un servicio al vector de servicios asociados a la aeronave.

7. `void addDestiny(string destiny)`: Agrega un destino al vector de destinos asociados a la aeronave.

8. `void landing() override`: Implementación de la acción de aterrizaje específica para un jet. Este método anula el método virtual `landing` definido en la clase base `Aircraft`.

9. `void taking_off() override`: Implementación de la acción de despegue específica para un jet. Este método anula el método virtual `taking_off` definido en la clase base `Aircraft`.

La clase `Jet` representa un tipo específico de aeronave (jet) que hereda los atributos y métodos de la clase base `Aircraft` y agrega atributos y comportamientos específicos relacionados con los jets, como el propietario, los servicios y los destinos asociados.

##### 2.2.3. Helicopter
Clase `Helicopter` (Hereda de `Aircraft`):

**Atributos adicionales:**
1. `int rotors`: La cantidad de rotores del helicóptero.

2. `int elevationCapacity`: La capacidad de elevación del helicóptero.

3. `int useType`: El tipo de uso del helicóptero.

**Métodos adicionales:**
1. `Helicopter(...)`: Constructor parametrizado que inicializa los atributos de la clase `Helicopter` al crear una instancia. Este constructor también llama al constructor de la clase base `Aircraft` para inicializar sus atributos.

2. `int getRotors()`: Devuelve la cantidad de rotores del helicóptero.

3. `int getElevationCapacity()`: Devuelve la capacidad de elevación del helicóptero.

4. `int getUseType()`: Devuelve el tipo de uso del helicóptero.

5. `void setRotors(int rotors)`: Establece la cantidad de rotores del helicóptero.

6. `void setElevationCapacity(int elevationCapacity)`: Establece la capacidad de elevación del helicóptero.

7. `void setUseType(int useType)`: Establece el tipo de uso del helicóptero.

8. `void landing() override`: Implementación de la acción de aterrizaje específica para un helicóptero. Este método anula el método virtual `landing` definido en la clase base `Aircraft`.

9. `void taking_off() override`: Implementación de la acción de despegue específica para un helicóptero. Este método anula el método virtual `taking_off` definido en la clase base `Aircraft`.

La clase `Helicopter` representa un tipo específico de aeronave (helicóptero) que hereda los atributos y métodos de la clase base `Aircraft` y agrega atributos y comportamientos específicos relacionados con los helicópteros, como la cantidad de rotores, la capacidad de elevación y el tipo de uso.

##### 2.3. AirCraftFactory
La clase `AircraftFactory` es una fábrica de objetos `Aircraft` que proporciona métodos estáticos para crear instancias de diferentes tipos de aeronaves (`Airplane`, `Helicopter` y `Jet`). Estos métodos de creación permiten instanciar objetos de aeronaves con diferentes atributos según el tipo de aeronave que se desee crear.

**Métodos estáticos:**
1. `static Aircraft* createAirplane(...)`: Este método estático crea y devuelve una instancia de un objeto `Airplane` con los atributos proporcionados.

2. `static Aircraft* createHelicopter(...)`: Este método estático crea y devuelve una instancia de un objeto `Helicopter` con los atributos proporcionados.

3. `static Aircraft* createJet(...)`: Este método estático crea y devuelve una instancia de un objeto `Jet` con los atributos proporcionados.

Cada método de creación toma una serie de parámetros que representan los atributos específicos de cada tipo de aeronave y utiliza esos parámetros para construir y retornar un objeto de la clase correspondiente.

Esta fábrica permite crear diferentes tipos de aeronaves de manera eficiente y flexible, ya que encapsula la lógica de creación de objetos de aeronaves en métodos estáticos reutilizables.

##### 2.4. Airline
Clase `Airline`:

**Atributos:**
1. `string name`: El nombre de la aerolínea.

2. `map<int, Aircraft> mapa`: Un mapa que almacena las aeronaves asignadas a la aerolínea, donde la clave es el identificador único de la aeronave (entero) y el valor es un objeto de la clase `Aircraft`.

3. `vector<int> vec_id`: Un vector que almacena los identificadores únicos de las aeronaves asignadas a la aerolínea.

**Métodos:**
1. `Airline()`: Constructor por defecto de la clase `Airline`.

2. `Airline(string name)`: Constructor que recibe el nombre de la aerolínea y lo asigna al atributo `name`.

3. `string getName()`: Devuelve el nombre de la aerolínea.

4. `void setName(string name)`: Establece el nombre de la aerolínea.

5. `void addAircraft(Aircraft aircraft)`: Agrega una aeronave al mapa `mapa` de la aerolínea. El identificador único de la aeronave se utiliza como clave en el mapa.

6. `void assignAircraftToFlight(vector<Aircraft*> aircrafts, vector<Flight*> flights)`: Asigna aeronaves a vuelos en función de ciertas condiciones. Esta función toma dos vectores como parámetros: uno que contiene punteros a objetos de tipo `Aircraft` y otro que contiene punteros a objetos de tipo `Flight`. Luego, realiza asignaciones de aeronaves a vuelos basadas en ciertas condiciones (no proporcionadas en el código) y actualiza los atributos de las aeronaves y vuelos en consecuencia.

La clase `Airline` se utiliza para representar una aerolínea y gestionar las asignaciones de aeronaves a vuelos en el contexto de la aerolínea.

##### 2.5. AirTrafficControler
Clase `AirTrafficControler`:

**Atributos:**
1. `vector<Aircraft*> aircrafts`: Un vector que almacena punteros a objetos de tipo `Aircraft`, que representan las aeronaves bajo el control del controlador de tráfico aéreo.

2. `vector<Gate*> gates`: Un vector que almacena punteros a objetos de tipo `Gate`, que representan las puertas de embarque bajo el control del controlador de tráfico aéreo.

3. `map<int, int> airCraftLocations`: Un mapa que almacena información sobre la ubicación de las aeronaves controladas, donde la clave es el identificador único de la aeronave (entero) y el valor es alguna información de ubicación (entero) relacionada con la aeronave.

**Métodos:**
1. `AirTrafficControler()`: Constructor por defecto de la clase `AirTrafficControler`.

2. `AirTrafficControler(vector<Aircraft*> aircrafts, vector<Gate*> gates)`: Constructor que recibe vectores de aeronaves y puertas de embarque y los asigna a los atributos correspondientes.

3. `vector<Aircraft*> getAircrafts()`: Devuelve el vector de aeronaves controladas.

4. `vector<Gate*> getGates()`: Devuelve el vector de puertas de embarque controladas.

5. `void setVecGates(vector<Gate*> gates)`: Establece el vector de puertas de embarque.

6. `void setVecAircrafts(vector<Aircraft*> aircrafts)`: Establece el vector de aeronaves.

7. `void permisson(bool permisson, int id)`: Realiza alguna operación relacionada con el permiso de una aeronave específica identificada por su ID. Los detalles exactos de esta operación no se proporcionan en el código.

8. `void addAircraft(Aircraft *aircraft)`: Agrega una aeronave al vector de aeronaves controladas.

9. `void removeAircraft(int id)`: Elimina una aeronave del vector de aeronaves controladas según su ID.

10. `void assingGate(Flight &flight)`: Asigna una puerta de embarque a un vuelo específico. Los detalles de esta asignación no se proporcionan en el código.

11. `void notify()`: Realiza una notificación relacionada con el control de tráfico aéreo. Los detalles exactos de esta notificación no se proporcionan en el código.

La clase `AirTrafficControler` se utiliza para representar un controlador de tráfico aéreo y gestionar la interacción y el control de aeronaves y puertas de embarque en el contexto de un aeropuerto o un sistema de tráfico aéreo.

##### 2.6. Flight
Clase `Flight`:

**Atributos:**
1. `int numberFlight`: El número de vuelo.

2. `string Destiny`: El destino del vuelo.

3. `int numberPassengers`: El número de pasajeros en el vuelo.

4. `string departureDate`: La fecha de salida del vuelo.

5. `string arrivalDate`: La fecha de llegada del vuelo.

6. `string Origen`: El lugar de origen del vuelo.

7. `int seats`: La cantidad de asientos disponibles en el vuelo.

8. `bool asignado`: Un indicador que representa si el vuelo está asignado o no.

9. `vector<Passenger> passengers`: Un vector que almacena objetos de tipo `Passenger`, que representan a los pasajeros del vuelo.

10. `vector<Crewmate> crewmates`: Un vector que almacena objetos de tipo `Crewmate`, que representan a los miembros de la tripulación del vuelo.

11. `bool gateAsigned`: Un indicador que representa si se ha asignado una puerta de embarque al vuelo.

**Métodos:**
1. `Flight()`: Constructor por defecto de la clase `Flight`.

2. `Flight(...)`: Constructor parametrizado que inicializa los atributos de la clase `Flight` al crear una instancia.

3. `int getNumberFlight()`: Devuelve el número de vuelo.

4. `int getSeats()`: Devuelve la cantidad de asientos disponibles en el vuelo.

5. `bool getAsignado()`: Devuelve si el vuelo está asignado.

6. `void setAsignado(bool asignado)`: Establece si el vuelo está asignado o no.

7. `void setgate(bool gateAsigned1)`: Establece si se ha asignado una puerta de embarque al vuelo.

8. `bool getGateAsigned()`: Devuelve si se ha asignado una puerta de embarque al vuelo.

9. `string getDestiny()`: Devuelve el destino del vuelo.

10. `int getNumberPassengers()`: Devuelve el número de pasajeros en el vuelo.

11. `string getDepartureDate()`: Devuelve la fecha de salida del vuelo.

12. `string getArrivalDate()`: Devuelve la fecha de llegada del vuelo.

13. `string getOrigen()`: Devuelve el lugar de origen del vuelo.

14. `void setNumberFlight(int numberFlight)`: Establece el número de vuelo.

15. `void setDestiny(string Destiny)`: Establece el destino del vuelo.

16. `void setNumberPassengers(int numberPassengers)`: Establece el número de pasajeros en el vuelo.

17. `void setDepartureDate(string departureDate)`: Establece la fecha de salida del vuelo.

18. `void setArrivalDate(string arrivalDate)`: Establece la fecha de llegada del vuelo.

19. `void setOrigen(string Origen)`: Establece el lugar de origen del vuelo.

20. `void addPassenger(Passenger passenger)`: Agrega un pasajero al vuelo.

21. `vector<Passenger> getPassengers()`: Devuelve un vector con los pasajeros del vuelo.

22. `void printInfo()`: Imprime información sobre el vuelo.

23. `void addCrewmates()`: Agrega miembros de la tripulación al vuelo.

La clase `Flight` se utiliza para representar información sobre vuelos y gestionar detalles relacionados con pasajeros, miembros de la tripulación y asignación de puertas de embarque.

##### 2.7. People
Clase `People`:

**Atributos:**
1. `string name`: El nombre de la persona.

2. `int id`: El identificador único de la persona.

3. `int number`: Un número relacionado con la persona (puede representar un número de teléfono u otro identificador).

4. `string birth`: La fecha de nacimiento de la persona.

5. `string gender`: El género de la persona.

6. `string email`: La dirección de correo electrónico de la persona.

**Métodos:**
1. `People()`: Constructor por defecto de la clase `People`.

2. `People(...)`: Constructor parametrizado que inicializa los atributos de la clase `People` al crear una instancia.

3. `string getName()`: Devuelve el nombre de la persona.

4. `int getId()`: Devuelve el identificador único de la persona.

5. `int getNumber()`: Devuelve el número relacionado con la persona.

6. `string getBirth()`: Devuelve la fecha de nacimiento de la persona.

7. `string getGender()`: Devuelve el género de la persona.

8. `string getEmail()`: Devuelve la dirección de correo electrónico de la persona.

9. `void setName(string name)`: Establece el nombre de la persona.

10. `void setId(int id)`: Establece el identificador único de la persona.

11. `void setNumber(int number)`: Establece el número relacionado con la persona.

12. `void setBirth(string birth)`: Establece la fecha de nacimiento de la persona.

13. `void setEmail(string email)`: Establece la dirección de correo electrónico de la persona.

14. `void setGender(string gender)`: Establece el género de la persona.

La clase `People` se utiliza para representar la información personal de una persona y proporciona métodos para acceder y modificar sus atributos. Puede ser utilizada como clase base para otras clases que representen tipos específicos de personas, como pasajeros o miembros de la tripulación en un sistema relacionado con vuelos.

##### 2.7.1. Passenger
Clase `Passenger` (Hereda de `People`):

**Atributos adicionales:**
1. `int numBags`: La cantidad de maletas que lleva el pasajero.

2. `string medical_info`: Información médica relacionada con el pasajero.

3. `string nationality`: La nacionalidad del pasajero.

**Métodos adicionales:**
1. `Passenger()`: Constructor por defecto de la clase `Passenger`.

2. `Passenger(...)`: Constructor parametrizado que inicializa los atributos de la clase `Passenger` al crear una instancia. Este constructor también llama al constructor de la clase base `People` para inicializar sus atributos.

3. `int getNumBags()`: Devuelve la cantidad de maletas del pasajero.

4. `string getMedicalInfo()`: Devuelve la información médica del pasajero.

5. `string getNationality()`: Devuelve la nacionalidad del pasajero.

6. `void setNumBags(int numBags)`: Establece la cantidad de maletas del pasajero.

7. `void setMedicalInfo(string medical_info)`: Establece la información médica del pasajero.

8. `void setNacionality(string nationality)`: Establece la nacionalidad del pasajero.

9. `void printInfo()`: Imprime información sobre el pasajero.

La clase `Passenger` se utiliza para representar la información de un pasajero, incluyendo detalles específicos relacionados con el número de maletas, la información médica y la nacionalidad. Esta clase hereda los atributos y métodos de la clase base `People`, que representa la información personal común a todas las personas, incluyendo pasajeros.

##### 2.7.2. Crewmate
Clase `Crewmate` (Hereda de `People`):

**Atributos adicionales:**
1. `string charge`: El cargo o posición que ocupa el miembro de la tripulación (por ejemplo, piloto, asistente de vuelo, etc.).

2. `int years_experience`: La cantidad de años de experiencia laboral del miembro de la tripulación.

3. `int daily_hours`: El número de horas de trabajo diarias del miembro de la tripulación.

**Métodos adicionales:**
1. `Crewmate(...)`: Constructor parametrizado que inicializa los atributos de la clase `Crewmate` al crear una instancia. Este constructor también llama al constructor de la clase base `People` para inicializar sus atributos.

2. `string getCharge()`: Devuelve el cargo del miembro de la tripulación.

3. `int getYearsExperience()`: Devuelve la cantidad de años de experiencia del miembro de la tripulación.

4. `int getDailyHours()`: Devuelve el número de horas de trabajo diarias del miembro de la tripulación.

5. `void setCharge(string charge)`: Establece el cargo del miembro de la tripulación.

6. `void setYearsExperience(int years)`: Establece la cantidad de años de experiencia del miembro de la tripulación.

7. `void setDailyHours(int hours)`: Establece el número de horas de trabajo diarias del miembro de la tripulación.

La clase `Crewmate` se utiliza para representar a los miembros de la tripulación en un contexto relacionado con vuelos. Hereda los atributos y métodos de la clase base `People`, que representa la información personal común a todas las personas, incluyendo miembros de la tripulación.

##### 2.8. gate
Clase `gate`:

**Atributos:**
1. `int id`: El identificador único de la puerta de embarque.

2. `bool available`: Un indicador que representa si la puerta de embarque está disponible o no.

3. `string location`: La ubicación de la puerta de embarque.

4. `string boardingHour`: La hora de embarque en la puerta de embarque.

5. `Flight flight`: Un objeto de tipo `Flight` que representa el vuelo asociado a la puerta de embarque.

6. `vector<Flight> recordedFlights`: Un vector que almacena objetos de tipo `Flight`, que representan los vuelos registrados en la puerta de embarque.

**Métodos:**
1. `Gate()`: Constructor por defecto de la clase `Gate`.

2. `Gate(...)`: Constructor parametrizado que inicializa los atributos de la clase `Gate` al crear una instancia.

3. `void setFlight(Flight flight)`: Establece el vuelo asociado a la puerta de embarque.

4. `Flight getFlight()`: Devuelve el vuelo asociado a la puerta de embarque.

5. `int getFlightid()`: Devuelve el identificador único del vuelo asociado a la puerta de embarque.

6. `void addRecordedFlight(Flight flight)`: Agrega un vuelo al vector de vuelos registrados en la puerta de embarque.

7. `vector<Flight> getRecordedFlights()`: Devuelve un vector con los vuelos registrados en la puerta de embarque.

8. `int getId()`: Devuelve el identificador único de la puerta de embarque.

9. `bool getAvailable()`: Devuelve si la puerta de embarque está disponible.

10. `string getLocation()`: Devuelve la ubicación de la puerta de embarque.

11. `string getBoardingHour()`: Devuelve la hora de embarque en la puerta de embarque.

12. `void setId(int id)`: Establece el identificador único de la puerta de embarque.

13. `void setAvalible(bool available)`: Establece si la puerta de embarque está disponible o no.

14. `void setLocation(string location)`: Establece la ubicación de la puerta de embarque.

15. `void setBoardingHour(string boardingHour)`: Establece la hora de embarque en la puerta de embarque.

La clase `Gate` se utiliza para representar la información de una puerta de embarque y su estado de disponibilidad, así como para gestionar los vuelos asociados y los vuelos registrados en esa puerta de embarque en un contexto relacionado con aeropuertos y vuelos.


### 3. Funcionalidades

##### 3.1. Controlador Aéreo

3.1.1. Asignación de puertas de embarque 

Para realizar una asignación de puertas de embarque, siga estos pasos:
1.	Ingresar como empleado en el menú principal
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/welcome%20to%20the%20airport.png)

**(void menu(vector<string> Destinations)**
Este menú se encuentra dentro de una función llamada Menú del archivo airport.cpp, el programa funciona con un ciclo while por el cual se accede con la variable cin >> desicion; que permite inicial el programa o finalizarlo; luego haber inicializado el programa le pregunta con un condicional if; si es un empleado un viajero; en caso de elegir la opción 1; entra en el condicional del if y le permite entrar a otro condicional anidado 

![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image003.png)
2.	Ingresar a través de la opción torre de control
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image005.png)
Una vez accede a la opción de empleado dentro del while; y selecciona la torre de control; un condicional if(password==password_control_tower) ; lo que hace es restringir las opciones avanzadas que tienen acceso a las funciones internas del aeropuerto; funciones que hacen referencia al manejo de vuelos y aeronaves; funciones tales como:
        `void setVecGates(vector<Gate*> gates)`;
        `void setVecAircrafts(vector<Aircraft*> aircrafts)`;
        `void permisson(bool permisson, int id)`;
        `void addAircraft(Aircraft *aircraft)`;
        `void removeAircraft(int id)`;
        `void assingGate(Flight &flight)`;
        `void notify()`;

3. Al acceder a la torre de control a través de una contraseña, le pide que seleccione la opción 2 de Assigned gate
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image007.png)
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image009.png)
Internamente el programa ingresa al condicional else if(sel == 2); donde se encuentra un ciclo for que permite mostrar en la terminal todos los vuelos disponibles que están almacenados en un vector de tipo <Flight>.
Después de que el controlador aéreo ve todos los vuelos; se usa un cin >> flight_selected; 
lo que le permite recibir el numero del vuelo; y así buscar una aeronave
4. El programa le muestra al controlador aéreo todos los vuelos disponibles; y la opción que ingrese el número de vuelo deseado para asignar; para lo cual se usa un ciclo con for con la condición `(flights[i]->getNumberFlight() == flight_selected && flights[i]->getGateAsigned() == false)`; lo que permite verificar el atributo numero de vuelo con la opción selecciona por el controlador aéreo; también se verifica que el gate al que va a asignar este libre; ósea su atributo este (gate_available == false); si da el caso de que todas las condiciones se cumplan le permite al controlador asignar una puerta de embarque.
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image011.png)
5. Después de seleccionar el vuelo, le muestra las puertas disponibles; y que seleccione la puerta que desea para el respectivo vuelo
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image013.png)
    1.	Declara una función llamada assingGate en la clase AirTrafficControler, que toma un objeto de tipo Flight como parámetro.

    2.	Declara una variable local llamada selectedGate para almacenar la puerta de embarque seleccionada.

    3.	Inicia un bucle for que recorre todas las puertas de embarque en el vector gates. El bucle se ejecutará desde i = 0 hasta i < this->gates.size().

    4.	Dentro del bucle for, verifica si una puerta de embarque está disponible. Esto se hace llamando al método getAvailable() en el objeto gates[i], que parece ser una instancia de alguna clase relacionada con las puertas de embarque. Si la puerta de embarque está disponible, muestra un mensaje que indica que la puerta está disponible para su selección, junto con su número de identificación.

    5.	Después de mostrar las puertas de embarque disponibles, el programa espera la entrada del usuario mediante cin, lo que significa que el usuario debe seleccionar una puerta de embarque eligiendo el número correspondiente.

    6.	Luego, el programa utiliza el número seleccionado para acceder a la puerta de embarque correspondiente en el vector gates (teniendo en cuenta que los índices de los vectores comienzan en 0), y realiza las siguientes acciones:

    7.	Llama al método setFlight(flight) en la puerta de embarque seleccionada, lo que parece asignar el vuelo a esa puerta de embarque.
    8.	Llama al método setAvalible(false) en la puerta de embarque seleccionada para marcarla como no disponible.
    9.	Llama al método addRecordedFlight(flight) en la puerta de embarque seleccionada, que parece registrar el vuelo en algún lugar.
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image015.png)

6. Después de haber seleccionado una puerta; el programa le asigna a esa puerta al vuelo y regresa al menú principal
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image017.png)
##### 2.1.2. Notificación de las aeronaves en el aire – Interfase del usuario
1. Después de haber accedido a la torre de control; como un empleado, el programa le pide que Seleccione la opción de notify
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image019.png)
2. El programa permite a todas las aeronaves notificar su ubicación, y le muestra al controlador aéreo el id de la aeronave, su altitud; solo sirve si la aeronave se encuentra en el aire  
3. Después de eso; el programa le lleva al menú principal 
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image021.png)

##### 3.1.2. Notificación de las aeronaves en el aire – codificación 

Este código realiza las siguientes acciones:

![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image022.png)
1. Lee una variable `sel` desde la entrada estándar utilizando `cin`.
2. Comprueba si el valor de `sel` es igual a 1 (`sel == 1`).
3. Si `sel` es igual a 1, realiza las siguientes acciones:
   - Llama a la función `atc->notify()`.
   - Muestra un separador y un mensaje que indica que la ubicación de las aeronaves ha sido actualizada.
   - Itera a través de las aeronaves en el sistema (obtenidas a través de `atc->getAircrafts()`).
   - Para cada aeronave que está volando (`getFlying() == true`), muestra el identificador de la aeronave y llama a `atc->getAircrafts()[i]->printLocation()` para imprimir su ubicación.

En resumen, este código permite al usuario seleccionar una opción (presumiblemente mediante la variable `sel`) y, si la opción es igual a 1, notifica al sistema de control de tráfico aéreo (ATC), actualiza la ubicación de las aeronaves y muestra la ubicación de las aeronaves que están volando.

##### 2.1.3. Despegue y aterrizaje de aeronaves -- -Interfase de usuario
1. Después de acceder a través de la opción de empleado, torre de control; se rige por la opción de Permission.
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image025.png)
2. Después de acceder a la opción Permission, le pide el id de la aeronave; y le pregunta si le da permiso para despegar o aterrizar. Esto se maneja con un 0 y un 1; en caso de que se digite 0; la aeronave no cuenta con el permiso y si se digita un 1; tiene permiso de realizar la acción.
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image027.png)
3. En el caso del 1; se selecciono una nave que estaba en el aeropuerto y se le concedió el permiso de realizar el despegue
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image029.png)

##### 3.1.3. Despegue y aterrizaje de aeronaves – Codificación

Este código es una función llamada `AirTrafficControler::permisson`, que funciona así:

![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image030.png)
1. La función toma dos parámetros como entrada: un valor booleano `permisson` (que parece indicar si se otorga o revoca un permiso) y un entero `id` (que representa el identificador de una aeronave).
2. Inicia una variable `i` en 0 y una variable booleana `found` en `false` para realizar un bucle de búsqueda en el vector `aircrafts`.
3. Realiza un bucle `while` que recorre el vector `aircrafts` mientras `i` es menor que el tamaño del vector y `found` es `false`. El propósito de este bucle es buscar una aeronave con el identificador `id` especificado.
4. Dentro del bucle, verifica si el identificador de la aeronave en la posición `i` del vector `aircrafts` coincide con el `id` proporcionado. Si es así, actualiza el permiso de esa aeronave llamando al método `updatePermission(permisson)` en la aeronave y establece `found` en `true` para indicar que se ha encontrado la aeronave.
5. Después de salir del bucle de búsqueda, verifica si `found` es `false`. Si es así, muestra un mensaje que indica que la aeronave no fue encontrada.
6. Si `permisson` es `true`, lo que implica que se ha otorgado el permiso y la aeronave se ha encontrado y actualizado, se realiza una serie de acciones adicionales:
   - Verifica si la aeronave (en la posición `i-1`) no está volando (`getFlying()` es `false`).
   - Si la aeronave no está volando, llama a la función `removeAircraft(id)` para eliminar la aeronave del sistema.
   - Luego, itera a través del vector `gates` y busca las puertas de embarque asociadas a la aeronave con el `id` proporcionado. Si encuentra una coincidencia, establece la disponibilidad de esa puerta de embarque en `true`.
En resumen, esta función busca una aeronave por su identificador en el vector `aircrafts`, actualiza su permiso si se encuentra y realiza acciones adicionales si el permiso es `true`, como eliminar la aeronave y liberar puertas de embarque asociadas si la aeronave no está volando.

El código a continuación usa uso de la función explicada anteriormente `AirTrafficControler::permisson`, y funciona solicitando al controlador aéreo con un identificador (ID) de una aeronave y una autorización (permiso) para dicha aeronave, probablemente como parte de un sistema de control de tráfico aéreo (ATC). Aquí está una descripción paso a paso de lo que hace:
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image032.png)
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image034.png)
1. Declara dos variables locales, `id` (para el identificador de la aeronave) y `permission` (para la autorización).
2. Muestra un separador (`printf("-----------------------------------------------------------\n");`) para dar una apariencia más ordenada en la salida.
3. Solicita al usuario que ingrese el identificador de la aeronave con el mensaje "Please enter the id of the aircraft" y almacena la entrada del usuario en la variable `id` mediante `cin`.
4. Muestra otro separador.
5. Utiliza un bloque `try-catch` para manejar excepciones. Dentro del bloque `try`, solicita al usuario que ingrese la autorización (permiso) con el mensaje "Please enter the permission" y almacena la entrada del usuario en la variable `permission` mediante `cin`.
6. Después de ingresar la autorización, verifica si la `permission` ingresada es diferente de 0 y 1. Si no es así, lanza una excepción de tipo `invalid_argument` con el mensaje "Invalid permission".
7. Si la `permission` es 0 o 1, significa que la entrada fue válida. Llama a la función `atc->permisson(permission, id)` pasando la autorización y el identificador como argumentos.
8. Si se lanza una excepción (en caso de que la autorización sea inválida), el código en el bloque `catch` captura la excepción y muestra el mensaje de error utilizando `e.what()`.
9. Si la autorización es 0 o 1 (lo que significa que fue válida y se realizó la llamada a `atc->permisson()`), muestra un mensaje que indica que la autorización ha sido actualizada.

En resumen, este código solicita al usuario un identificador y una autorización para una aeronave, maneja posibles excepciones si la autorización no es válida y muestra un mensaje de confirmación si la autorización se actualiza correctamente. La funcionalidad exacta del código depende de la implementación de la función `atc->permisson()` y cómo se gestionan las autorizaciones dentro de esa función.

 #### 3.2. Aerolínea – interfase del usuario
 3.2.1. Asignación de vuelos a aeronaves
1. Después de acceder como empleado; selecciona la opción de empleado, y accedes como una aerolínea; a lo que le permite acceder a la asignación de vuelos; con el número 1.
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image036.png)
2. Al seleccionar la opción de Asignar vuelos; el programa toma todos los vuelos disponibles, sin avión y los asigna automáticamente; y termina mostrando a la aerolínea, todos los vuelos con el respectivo id del avión 


##### 3.2. Aerolínea – código Interno
3.2.1. Asignación de vuelos a aeronaves
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image038.png)
1. El código verifica si `sel2` es igual a 2 (`sel2 == 2`), lo que sugiere que el usuario ha seleccionado la segunda opción del menú.
2. Si `sel2` es igual a 2, muestra un mensaje con un encabezado y una lista de opciones. El mensaje incluye un título ("Select one option") y dos opciones numeradas:
   - Opción 1: "Asignar Avion a vuelo"
3. Luego, espera que el usuario ingrese una opción seleccionando un número con `cin` y lo almacena en la variable `sel`.
4. Si el usuario selecciona la opción 1 (`sel == 1`), llama a la función `assignAircraftToFlight` en la primera aerolínea (`airlines[0]`). Esta función parece asignar aeronaves a vuelos según ciertas condiciones, utilizando las aeronaves del objeto `atc` y los vuelos almacenados en el vector `flights`.
5. Después de ejecutar la función `assignAircraftToFlight`, muestra un separador en la salida estándar.
En resumen, este código proporciona una opción para que el usuario asigne aeronaves a vuelos y luego muestra un separador en la salida. La lógica detallada de la asignación de aeronaves a vuelos se encuentra en la función `assignAircraftToFlight`.
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image040.png)
    La función llamada `Airline::assignAircraftToFlight` que asigna aeronaves a vuelos específicos bajo ciertas condiciones. Aquí está una breve explicación de lo que hace:
    1. Muestra un mensaje "Aircrafts" en la salida para indicar que se está trabajando con aeronaves.
    2. Itera a través de un vector de vuelos (`flights`) en busca de vuelos que tengan "Cali" como origen.
    3. Para cada vuelo con origen en "Cali", se inicia un bucle `while` que recorre el vector de aeronaves (`aircrafts`) en busca de una aeronave adecuada para asignar al vuelo.
    4. Dentro del bucle, se verifica si una aeronave cumple con ciertas condiciones para ser asignada al vuelo. Estas condiciones incluyen:
   - La aeronave es de tipo "Airplane".
   - La aeronave no está volando (`getFlying() == false`).
   - La aeronave no tiene asignados más de 3 vuelos (`getvec_flights() < 3`).
    5. Si una aeronave cumple con estas condiciones, se agrega el vuelo a la aeronave llamando al método `addFlight(*flights[i])`, se marca el vuelo como asignado (`flights[i]->setAsignado(true)`) y se realiza un seguimiento de la aeronave en un mapa llamado `mapa` y un vector llamado `vec_id`. Si la aeronave ya existe en el mapa, se actualiza; de lo contrario, se agrega al mapa y al vector de identificadores.
    6. Una vez que se han asignado todas las aeronaves a los vuelos apropiados, se realiza otro bucle (`for`) para imprimir la lista de vuelos asignados a cada aeronave utilizando el método `printVec_flights()` en función de su identificador almacenado en `vec_id`.

En resumen, esta función busca vuelos con origen en "Cali" y asigna aeronaves a esos vuelos si cumplen con ciertas condiciones. Luego, muestra la lista de vuelos asignados a cada aeronave.

#### 3.3. Usuario

3.3.1. Reservar un vuelo – interfase del usuario
1. Primero lo lleva al menú principal; el usuario o viajero debería seleccionar la opción 2 que despliega el menú en el cual le solicita que llene sus datos para hacer un registro
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image042.png )

2. Luego de crear el registro del viajero; el programa le pregunta al usuario la ciudad a la que desea viajar, y le muestra los vuelos disponibles para esa ciudad
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image044.png)
3. Al usuario seleccionar su vuelo le muestra a el usuario su vuelo de reserva; y que ha sido exitosamente 
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image046.png)
4. En caso de que el vuelo no tenga asientos disponibles; Le mostrara un mensaje al usuario diciendo que no es posible hacer la reserva y le pedirá al usuario que seleccione otro vuelo en el cual si se pueda hacer la reserva
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image048.png)
5. Si se realiza el cambio de vuelo debería permitirle al usuario realizar su nueva reserva y ser agregado al vuelo
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image050.png)

3.3.1. Reservar un vuelo – codificación 
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image052.png)
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image054.png)
Al ingresar en el menú principal como usuario; se invoca un constructor sin parámetros; que esta codificado de tal manera que le pide a través de consola los datos principales para crear un objeto de clase pasajero; luego de eso le permite ingresar el destino y el sistema verifica si hay vuelos disponibles para ese destino
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image056.png)
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image058.png)

Esta parte del código permite a un usuario seleccionar un vuelo y agregar un pasajero a ese vuelo, siempre que haya asientos disponibles.
 ![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image060.png)
1. Se inicializa una variable booleana `available_flight` en `false`. Esta variable se utiliza para controlar si se ha encontrado un vuelo disponible para agregar al pasajero.
2. Se inicia un bucle `while` que se ejecutará mientras `available_flight` sea `false`. El propósito de este bucle es permitir que el usuario seleccione un vuelo y agregar un pasajero a ese vuelo si es posible.
3. Dentro del bucle, se muestra un mensaje solicitando al usuario que ingrese el número del vuelo que desea elegir (`"Type the number of the flight that you'd like to choose"`).
4. Se utiliza `scanf` para leer el número de vuelo ingresado por el usuario y almacenarlo en la variable `flight_selected`.
5. Se realiza un bucle `for` para buscar el vuelo correspondiente en el vector `flights` utilizando su número de vuelo (`getNumberFlight()`).
6. Si se encuentra un vuelo con el número seleccionado, se verifica si el vuelo tiene asientos disponibles (`getSeats() < 1`). Si no hay asientos disponibles, se muestra un mensaje que indica que no hay asientos disponibles en ese vuelo y se pide al usuario que seleccione un vuelo diferente.
7. Si hay asientos disponibles en el vuelo seleccionado, se agrega el pasajero (representado por `persona1`) al vuelo llamando a `flights[j]->addPassenger(*persona1)`. Además, se almacena el índice del vuelo actual en la variable `current_flight` y se establece `available_flight` en `true` para salir del bucle, ya que se ha encontrado un vuelo disponible.

En resumen, este código permite al usuario seleccionar un vuelo, verifica si hay asientos disponibles en ese vuelo y agrega un pasajero al vuelo seleccionado si hay asientos disponibles. Si no hay asientos disponibles, se le informa al usuario y se le pide que seleccione otro vuelo. 
![Menu de inicio](https://raw.githubusercontent.com/marco2712/fotos/main/Fotos%20proyecto%20poo/Airport%20Alfonso_files/image062.png)
La función llamada `addPassenger` dentro de la clase `Flight`, se encarga de agregar un pasajero al vuelo y reducir la cantidad de asientos disponibles en ese vuelo en 1. Aquí está una explicación más detallada:

1. `void Flight::addPassenger(Passenger passenger)`: Esta línea declara la función `addPassenger` que pertenece a la clase `Flight`. La función toma un parámetro de tipo `Passenger` llamado `passenger`, que representa al pasajero que se va a agregar al vuelo.
2. `passengers.push_back(passenger)`: Esta línea agrega el objeto `passenger` (el pasajero) al final del vector `passengers` que pertenece al objeto `Flight`. En otras palabras, el pasajero se agrega a la lista de pasajeros que están a bordo de este vuelo.
3. `this->seats -= 1;`: Esta línea reduce el número de asientos disponibles en el vuelo en 1. Esto se hace disminuyendo el valor del miembro de datos `seats` del objeto `Flight` en 1. Indica que un asiento se ha ocupado por el pasajero recién agregado.
En resumen, esta función toma un pasajero como entrada y lo agrega a la lista de pasajeros de un vuelo específico, al mismo tiempo que reduce la cantidad de asientos disponibles en ese vuelo en 1 para reflejar que un asiento ha sido ocupado.

### 4. Solución de Problemas Comunes
##### 4.1. No se puede abrir el programa
Si experimenta problemas para abrir el programa, asegúrese de que su sistema cumple con los requisitos del sistema mencionados en la sección 1.1. Si el problema persiste, comuníquese con nuestro equipo de soporte técnico.

##### 4.2. Errores en la creación de aeronaves y reservas
Si encuentra errores en la creación de reservas y aeronaves, verifique que haya ingresado la información del usuario correctamente. Si el problema persiste, póngase en contacto con nuestro equipo de soporte técnico para obtener ayuda.
### 5. Diagrama UML

Enlace de drawio con la relacion entre las diferentes clases y suclases 
 https://app.diagrams.net/#G1cGocRfbN9pkQDUm0T99rlcJZp0B5Z3Np
### 6. Contacto y Soporte Técnico

Si tiene alguna pregunta o necesita asistencia, no dude en ponerse en contacto con nuestro equipo de soporte técnico en chino123@javerianacali.edu.co, marcor27@javerianacali.edu.co, o llamando al +573137049579.


