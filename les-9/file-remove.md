---
title: Les 9
layout: page
permalink: :path/:basename
nav_exclude: true
---

## File verwijderen
{: .text-green-100 .fs-6 }

Dit is de laatste stap in het CRUD process.  
Als een regel uit de database verwijderd wordt moet het gekoppelde bestand natuurlijk ook verwijderd worden.

---
### 1- Verwijder het bestand
Ga in de controller naar de `destroy` functie.  
Voordat je het `model` verwijderd moet je eerst het `bestand` verwijderen.  
Natuurlijk controleer je ook even of er wel een afbeelding is.  
Bijvoorbeeld: 
```php
    /**
     * Remove the specified resource from storage.
     */
    public function destroy(Model $model)
    {
        if ( ! empty($project->image ) ) {
            Storage::delete($project->image);
        }
        $project->delete();
        
        return redirect(route('model.index'));
    }
```

---
Dat is het, je hebt nu een mooie complete CRUD flow. 

---

{% include commit_push.md %}


