# Frontend Dockerfile
FROM node:18-alpine AS build
WORKDIR /app
COPY . .
RUN npm ci && npm run build

FROM nginx:alpine
COPY --from=build /app/dist/angular-ecommerce/browser /usr/share/nginx/html/
EXPOSE 81
CMD ["nginx", "-g", "daemon off;"]