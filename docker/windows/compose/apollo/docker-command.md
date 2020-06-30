docker run -p 8080:8080 \
    -e SPRING_DATASOURCE_URL="jdbc:mysql://localhost:3306/ApolloConfigDB?characterEncoding=utf8" \
    -e SPRING_DATASOURCE_USERNAME=root -e SPRING_DATASOURCE_PASSWORD=123456 \
    -d -v D:\app\apollo\tmp\logs:/opt/logs --name apollo-configservice apolloconfig/apollo-configservice