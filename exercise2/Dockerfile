# step 1: Compile and Build angular codebase
#Use official node image as the base image
FROM node:latest as build
#Set the working directory
WORKDIR /usr/local/app
#Add the source code to app
COPY . .
#Install all the dependencies
RUN npm install
#Generate the build of the application
RUN npm run build


#step 2: Serve app with nginx server
FROM nginx:latest
#copy the build output to replace the default nginx contents
COPY --from=build /usr/local/app/dist/docker-example/browser /usr/share/nginx/html
#Expose port 80
EXPOSE 80
