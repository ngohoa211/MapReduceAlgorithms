# MapReduceAlgorithms

# Hướng dẫn build file java
project sử dụng maven cho quản lý thư vieenh:
-sửa file pom.xml:
<configuration>
					<archive>
						<manifest>
							<mainClass>path.to.MainClass</mainClass>
						</manifest>
					</archive>
					<descriptorRefs>
						<descriptorRef>jar-with-dependencies</descriptorRef>
					</descriptorRefs>
</configuration>
sửa "path.to.MainClass" thành đường dẫn tới thuật toán muốn build.  
ví dụ với thuật toán common friend "path.to.MainClass" -> "CommonFriends.CommonFriendsDriver"  -chạy lệnh build  $mvn clean compile assembly:single
# Hướng dẫn chạy với hadoop:
Sau khi build file jar xong, chạy job với hadoop dùng lệnh:
$HADOOP_HOME/bin/hadoop jar $APP_JAR $PROG $INPUT $OUTPUT [argument1,argument2…]  
Trong đó:
HADOOP_HOME: địa chỉ home của hadoop
$APP_JAR là file .jar đã biên dịch
$PROG địa chỉ class chứa hàm main (ở đây là địa chỉ của TriangleCounterDriver )
$INPUT $OUTPUT : file input đầu vào, địa chỉ output
argument1, argument2… : các tham số nếu cần, 
