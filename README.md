import java.util.Arrays;
import java.util.Comparator;
import java.util.HashMap;
import java.util.Map;
public class ActorWithMaxRoles {
public static void main(String[] args) {
Map<String, Integer> rolesPerActor = new HashMap<>();
String[] actorsAndRoles = {
“Tom Hanks”, “Forrest Gump”, “John Travolta”, “Saturday Night Fever”,
“Leonardo DiCaprio”, “The Wolf of Wall Street”, “Brad Pitt”, “Fight Club”,
“Julia Roberts”, “Pretty Woman”, “Cameron Diaz”, “Charlie’s Angels”
};
    for (String actorAndRole : actorsAndRoles) {
        String[] actorAndRoleSplit = actorAndRole.split(" ");
        rolesPerActor.put(actorAndRoleSplit[0], rolesPerActor.getOrDefault(actorAndRoleSplit[0], 0) + 1);
    }

    // Сортировка актеров по количеству ролей с помощью компаратора
    Comparator<String> roleCountComparator = Comparator.
    comparing(rolesPerActor::get);
    Arrays.sort(rolesPerActor.keySet().toArray(), roleCountComparator.reversed());
    System.out.println("Actor with the maximum number of roles: " + rolesPerActor.get(rolesPerActor.keySet()
            .toArray()[0]));
}
}
В этом коде мы сначала создаем карту, в которой ключом является имя актера, а значением - количество сыгранных им ролей. Затем мы проходим по списку актеров и ролей и увеличиваем счетчик ролей для каждого актера.
Затем мы сортируем актеров по количеству сыгранных ролей и выводим актера с максимальным количеством ролей.
