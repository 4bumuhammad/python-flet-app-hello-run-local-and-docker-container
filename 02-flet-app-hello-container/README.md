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




### Result :

<p align="center">
    <img src="./gambar-petunjuk/under_construction_small.png" alt="under_construction_small" style="display: block; margin: 0 auto;">
</p>
<p align="center">web</p>

