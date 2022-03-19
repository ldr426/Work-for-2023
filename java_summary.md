## Math

Math.**abs**(x); 
Math.**sqrt**(x);
Math.**pow**(e,n);

Math.**min**(a, b);
Math.**max**(a, b);

## Integer

if (num > **Integer.MIN_VALUE**) {
    // ...
}
if (num < **Integer.MAX_VALUE**) {
    // ...
}

String s = "123";
int num = Integer.**parseInt**(s); 	// num == 123
int num=Integer.**valueOf**(s);	// num == 123

## Character

Character.**isDigit**(c);
Character.**isLetter**(c);
Character.**isLowerCase**(c);

Character.**toLowerCase**(c);
Character.**toUpperCase**(c);

## String

String s = "foobar";
s.**<u>charAt</u>**(3); // 'b'
s.**contains**("bar"); //true
s.contains("xxx"); // false
s.**indexOf**('o'); // 1
s.indexOf('o', 2); // 2
s.**lastIndexOf**('o'); // 2
s.lastIndexOf('o', 1); // 1

s.**substring**(start, end); // **[start, <u>end)</u>**
s.**toCharArray**();
s.toLowrCase();
s.toUpperCase();
s.trim(); 	//eliminates leading and trailing spaces
s.**valueOf**(obj); obj: int/float...

String m1 = String.join("-", "Java", "is", "cool");// "Java-is-cool"
List<String> strings = List.of("Java", "is", "cool");
String m2 = String.join(" ", strings); // "Java is cool"

## StringBuilder

StringBuilder sb = new **StringBuilder**("foobar");

sb.**append**("x"); // "foobarx"
sb.length(); // 7
sb.**reverse**(); // "xraboof"
sb.**delete**(0, 3); // "boof"
sb.deleteCharAt(3); // "boo"
sb.**insert**(2, "abc"); // "boabco"
sb.**setCharAt**(1, "y") // "byabco"
sb.charAt(4); // 'c'
sb.**toString**();

sb.setLength(0); // ""

## Collections

Collections.reverse(list);
Collections.min(list);
Collections.max(list);

## Arrays

String[] a = new String[100];
String[] b = **Arrays.copyOf**(a, **a.length**);
List<String> list = **Arrays.asList**(a);
String[] b = (String[]) list.**toArray**(**new** String[**list.size()**]);
String[] c = **Arrays.copyOfRange**(a, start, end); [start, end)
**Arrays.fill**(a, "x");
**Arrays.equals**(a1, a2);
**<u>Arrays.sort</u>**(array, begin, end+1); // [start, end)
**<u>Arrays.sort</u>**(array, cmp); // cmp: check PriorityQueue part

int[] ints = {1, 2, 3};
System.out.println(ints); // [I@379619aa
System.out.println(**Arrays.toString**(ints)); // [1, 2, 3]

## Set

Set<Integer> s1 = new HashSet<>();
s1.**addAll**(**Arrays.asList**(1, 2, 3));

Set<Integer> s2 = new HashSet<>(Arrays.asList(1, 2, 3));
s1.**add**(3);
s1.**contains**(4);
s1.**remove**(3);

for (int num: s2) {
    // ...
}

## List

List<Integer> nums = new **ArrayList**<>(); // []
nums.**add**(5); // [5]
numd.add(7); // [5, 7]
nums.add(0, 6); // [6, 5, 7]
nums.**get**(1); // 5 // random query
nums.**remove**(1); // [6, 7]
nums.subList(1, 2); // [7]

List<Integer> **queue** = new **LinkedList**<>(); // not support for random query
queue.add(1); // [1]
queue.add(2); // [1, 2]
queue.**addFirst**(3); [3, 1, 2] 	//queue, stack and deque
queue.addLast(5); // [3, 1, 2, 5]
queue.poll(); // 3
queue.**pollFirst**(); // 1
queue.pollLast(); 5

## Map

Map<String, Integer> map = new HashMap<>();
map.**put**("foo", 123);
map.**putIfAbsent**("x", 9); 
map.**get**("foo"); // 123
map.**getOrDefault**("bar", 0); // 0
map.**containsKey**("foo"); // true
for (**Map.Entry**<String, Integer> entry : map.**entrySet**()) {
    **entry.getKey**();
    **entry.getValue**();
}

## Deque

Deque<Integer> stack = new **ArrayDeque**<>(); 
stack.push(1); // [1]
stack.push(2); // [2, 1]
stack.peek(); // 2
stack.isEmpty(); // false
stack.pop(); // 2

## PriorityQueue

PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.**add**(3); pq.add(1); pq.add(5);
pq.**poll**();
pq.**peek**();
pq.**clear**();

PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> b - a);
**lambda** :for **wrapper class or multi-array**  but not for basic type

PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> b.compareTo(a));
PriorityQueue<Node> pq = new PriorityQueue<>(new Comparator<Node>(){
    public int compare(Node n1, Node n2) {
        return n1.value - n2.value;
    }
})

## Scanner

**Scanner** sc = new Scanner(**System.in**);

int n1 = sc.**nextInt**();
double n2 = sc.nextDouble();
String s = sc.**nextLine**();

System.out.println("String: " + s);
System.out.println("Double: " + n2);
System.out.println("Int: " + n1);