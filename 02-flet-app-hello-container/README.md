# Flet app HELLO run Docker container


### Code :

    import flet as ft


    def main(page: ft.Page):


        appbar = ft.AppBar(
            title = ft.Text("Flet web app", size=45, color="white"),
            bgcolor = "blue"
        )

        page.vertical_alignment = ft.MainAxisAlignment.CENTER
        page.horizontal_alignment = ft.CrossAxisAlignment.CENTER

        content_1 = ft.Container(
            content = ft.Column([
                ft.Text("Hello From Flet", size=40)
            ])
        )

        content_2 = ft.Container(
            content = ft.Column([
                ft.Text("by Dhony Abu Muhammad", size=20)
            ])
        )


        page.add(appbar, content_1, content_2)


    ft.app(target=main,port=8080, view=None)

Notice the difference in the code section `ft.app(target=main,port=8080, view=None)`, this is to allow the application to be accessed from outside the container.


### &#x1F525; Build and run :


    ❯ docker build -t flethello .

    ❯ docker run -d --name flethello-app -p 8080:8080 flethello



    # list

    ❯ docker images

        REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
        flethello    latest    97cfbe970627   28 seconds ago   143MB


    ❯ docker ps -a --format "table {{.ID}}\t{{.Image}}\t{{.Status}}\t{{.Names}}\t{{.Ports}}"

        CONTAINER ID   IMAGE       STATUS          NAMES           PORTS
        ad55e0e0b92d   flethello   Up 29 seconds   flethello-app   0.0.0.0:8080->8080/tcp



### Result :

<p align="center">
    <img src="./gambar-petunjuk/ss_flet_web_app_container.png" alt="ss_flet_web_app_container" style="display: block; margin: 0 auto;">
</p>
<p align="center">web | app container</p>



### Notes : 

    ❯ docker --version

        Docker version 20.10.14, build a224086
