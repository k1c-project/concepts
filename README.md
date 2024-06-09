# Концепция k-)
__k-)__ или __k1C__ - контейнеры 1С. Инструмент для управление инфраструктурой 1С:Предприятие.

## Цели
Целью настоящего проекта является создание "cloud-like" инструмента для управленя инфраструктурой 1С:Предприятие для организаций с большим количеством информационных баз.

## Архитектура решения
В качестве прототипа используется облачная платформа [Microsoft Azure](https://azure.microsoft.com/), поскольку она прекрасно документирована и является одним из лидеров рынка облачных вычислений.  

### Компоненты системы
Основные компоненты облачной платформы Azure представлены на рисунке ниже:  

![](consistent-management-layer.png)  

Управление облачными ресурсами производится при помощи компонентов клиентского доступа (Azure portal, Azure PowerShell, Azure CLI, REST clients), которые  обращаются к службе управления ресурсами (Azure Resource Manager), которая в свою очередь и осуществляет управление облачными ресурсами.

Менеджер ресурсов осуществляет управление ресурсами не напрямую, а при помощи провайдеров ресурсов (см. рис. ниже).

![](arm_arch3.png)

SRP: Провайдер ресурсов хранилища (Storage Resource Provider), CRP: Провайдер ресурсов вычислений (Compute Resource Provider), NRP: Провайдер сетевых ресурсов (Network Resource Provider).

Такой подход позволяет достаточно гибко динамически изменять набор используемых ресурсов.

![](governance-1-15.png)
