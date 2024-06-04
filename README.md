
# Docker y Docker Compose en Raspberry Pi

**Fuente:** [Docker Documentation](https://docs.docker.com/engine/install/debian/)

### Instalar Docker y Docker Compose:

```sh
sudo curl -fsSL https://get.docker.com/ -o get-docker.sh
sudo sh get-docker.sh
```

### Añadir nuestro usuario al grupo Docker:

```sh
sudo usermod -aG docker ${USER}
```

### Reiniciar sistema:

```sh
sudo reboot
```

### Ejecutar un contenedor de prueba:

```sh
docker run hello-world
```

---

# Portainer en Raspberry Pi

**Fuente:** [Portainer Documentation](https://docs.portainer.io/start/install-ce/server/docker/linux)

### Crear volumen Docker que contendrá los datos gestionados por el servidor Portainer:

```sh
docker volume create portainer_data
```

### Descargar e instalar contenedor Portainer:

```sh
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

### Ver contenedores instalados:

```sh
docker ps
```

### Acceso a Portainer:

```
https://[IP de tu Raspberry Pi]:9443
```

**Ejemplo:** `https://192.168.1.10:9443`
