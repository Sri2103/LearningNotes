# Goroutine Template

go func() {
// work
}()

# Channel Template

ch := make(chan int)
ch <- 10
v := <-ch

# Worker Pool Template

for i := 0; i < n; i++ {
go worker(jobChan, resultChan)
}
