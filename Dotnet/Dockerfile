#Build Image
FROM mcr.microsoft.com/dotnet/core/sdk:2.2 As build-env
WORKDIR /usr/src/app
#Copy csproj an restore as ditinct layers
COPY *.csproj ./
RUN dotnet restore
#Copy everything else and buil
COPY . ./
RUN dotnet publish --configuration=Release -o pub 

#Runtime Image
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
WORKDIR /root
COPY --from=build-env /usr/src/app/pub ./app
ENV ASPNETCORE_URLS="http://*:5080"
WORKDIR /root/app
EXPOSE 5080/tcp
ENTRYPOINT ["dotnet", "DotnetAndDocker.dll"]