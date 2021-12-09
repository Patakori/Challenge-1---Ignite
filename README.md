Challenge 1 - Ignite

O desafio era criar as funções tarefas, concluido e deletar da aplicação To Do exitente:



Segue abaixo as funções criadas para o To Do funcionar:

function handleCreateNewTask() {
    // Crie uma nova task com um id random, não permita criar caso o título seja vazio.
    if(!newTaskTitle) return;

    const newTask = {
      id: Math.random(),
      title: newTaskTitle,
      isComplete:false,
    }

    setTasks(oldState => [...oldState, newTask]);
    setNewTaskTitle('')
  }

  function handleToggleTaskCompletion(id: number) {
    // Altere entre `true` ou `false` o campo `isComplete` de uma task com dado ID
    const newTasks = tasks.map(task => task.id === id ? {
      ...task,
      isComplete: !task.isComplete
    } : task)

    setTasks(newTasks)

  }

  function handleRemoveTask(id: number) {
    // Remova uma task da listagem pelo ID
    const filteredTasks = tasks.filter( task => task.id !== id);

    setTasks(filteredTasks)
  }
