Cancellation and timeouts

Завершение выполнения корутины

Для того, чтобы завершить корутину  val job = launch { } можно: job.cancel() - Завершает job с необязательным указанием причины отмены.

Все функции приостановки в kotlinx.coroutines можно отменить. Они проверяют отмену сопрограммы и выбрасывают CancellationException при отмене.

Если код содержит "долгие " вычисления, то job будет завершен только после того, как эти вычисления закончатся. Чтобы остановить работу, нужно внутри корутины вызвать isActive() - это свойство нужно для возможности отменить длительное вычисление.
Так же можно использовать yield()

Событие тайм-аута в withTimeout является асинхронным по отношению к коду, работающему в его блоке, и может произойти в любое время, даже прямо перед возвратом из блока тайм-аута.